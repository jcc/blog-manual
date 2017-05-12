# 文件系统 - 又拍云

默认文件系统为 `local`, 当然你可以扩展文件系统，将文件上传到云端上。此处我们使用又拍云的云存储，我们所使用的包：

* [JellyBool/flysystem-upyun](https://github.com/JellyBool/flysystem-upyun)

> 当然，博客系统内置了又拍云的文件系统只需修改 `app/filesystem.php` 的默认文件系统即可。

## 使用

修改 `app/filesystem.php` 文件为：

```php
'default' => 'upyun',
```

在 `.env` 文件添加相对应的配置：

```php
UPYUN_BUCKET=upyun-server-name // 服务名字
UPYUN_OPERATOR=oparator-name // 操作员的名字
UPYUN_PASSWORD=operator-password // 操作员的密码
UPYUN_DOMAIN=xxxxx.b0.upaiyun.com // 服务分配的域名
UPYUN_PROTOCOL=https // 服务使用的协议，如 http
```

配置好以上的配置即可愉快使用又拍云服务。
