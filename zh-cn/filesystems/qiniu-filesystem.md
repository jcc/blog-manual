# 文件系统 - 七牛

默认文件系统为 `local`, 当然你可以扩展文件系统，将文件上传到云端上。此处我们使用七牛的对象存储，我们所使用的包：

* [zgldh/qiniu-laravel-storage](https://github.com/zgldh/qiniu-laravel-storage)

## 安装及配置

安装 `zgldh/qiniu-laravel-storage` :

```shell
composer require zgldh/qiniu-laravel-storage
```

在 `config/app.php` 里面的 `providers` 数组， 加上：

```php
zgldh\QiniuStorage\QiniuFilesystemServiceProvider::class
```

将下面配置添加到 `filesystems.php` 文件到 `disks` 数组中，并配置好：

```php
'qiniu' => [
    'driver'  => 'qiniu',
    'domains' => [
        'default'   => 'xxxxx.clouddn.com', //你的七牛域名
        'https'     => 'dn-yourdomain.qbox.me',         //你的HTTPS域名
        'custom'    => 'static.abc.com',                //你的自定义域名
     ],
    'access_key'=> '',  //AccessKey
    'secret_key'=> '',  //SecretKey
    'bucket'    => '',  //Bucket名字
    'notify_url'=> '',  //持久化处理回调地址
],
```

> 你使用**七牛**文件系统时，切记将 `filesystems.php` 文件中的 `default` 的值修改为 `qiniu`, 否则一直是 `local`

## 重写 `FileManager` 方法

由于 `local` 文件系统获取数据的方法跟**七牛**的有所区别，在**七牛**中，`directory` 是没有任何作用，所以需要重写一下几个方法 ( `fileDetail`, `fileWebpath`, `getFileList` )，否则会获取不到文件列表以及信息。

在 `UploadManager.php` 文件中添加一下方法即可：

```php
/**
 * 获取所有文件
 * 
 * @param  string $path
 * @return array
 */
public function getFileList($path)
{
    $files = [];

    $filesContent = $this->disk->listContents($path, true);

    foreach ($filesContent as $file) {
        $files[] = $this->fileDetail($file);
    }

    return $files;
}

/**
 * 获取文件信息
 *
 * @param $path
 * @return array
 */
public function fileDetail($file)
{
    $path = $file['path'];

    return [
        'name' => $path,
        'fullPath' => $path,
        'webPath'  => $this->disk->privateImagePreviewUrl($path),
        'mimeType' => $this->fileMimeType($path),
        'size'     => $this->fileSize($path),
        'modified' => $this->fileModified($path)
    ];
}

/**
 * 获取图片预览 `URL`
 *
 * @param string $path
 * @return string
 */
public function fileWebPath($path)
{
    // 如果你使用的是七牛的私有 `bucket`, 则使用 `privateImagePreviewUrl` 方法获取图片预览 `url`
    return $this->disk->imagePreviewUrl($path);
}
```

> 你可以尝试在 `URL` 的 `folder` 参数输入正确的值，可以预览对应文件夹下的所有文件