# 开始

你可以在此简单学习如何去使用博客系统。

## 创建管理员

你注册一个新的账号，必须输入你的名字、邮箱和密码。

你可以很方便地通过 `blog:admin` 命令来创建一个新的管理员账号：

```shell
php artisan blog:admin
```

此外，你还可以在命令上加上额外的参数，`userId` 参数可查询对应 `userId` 的用户信息（用户名、邮箱以及是否为管理员），如果你想删除一个账号，你可以在 `userId` 参数后添加 `--delete` 的选项即可。 

```shell
php artisan {userId} --delete
```