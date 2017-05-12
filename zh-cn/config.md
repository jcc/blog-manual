# 配置

默认语言配置是*英语*， 如果你想将语言改为*中文*，你只需要将 `LOCALE` 配置加入到 `.env` 文件中即可：

```php
LOCALE=zh_cn #options: en/zh_cn
```

## `.env` 文件的配置列表：

| 关键字 | 描述 |
| --- | --- |
| MAIL_NOTIFICATION | 是否开启邮件通知发送（开启则需要设置邮件驱动），默认为 `false`，开启则设置为 `true` |
| DEFAULT_AVATAR | 设置站点的默认头像 |
| DEFAULT_ICON | 设置站点的 Favicon |
| ARTICLE_SHARE | 文章是否开放分享，如开启则设置为 `true`，否则为 `false` |
| DISCUSSION_SHARE | 讨论是否开放分享，如开启则设置为 `true`，否则为 `false` |
| SOCIAL_SHARE_SITES | 设置社交分享的方式 |
| SOCIAL_SHARE_MOBILE_SITES | 设置手机端社交分享的方式 |
| GOOGLE_OPEN | 如果你想开启 Google Analytics，你应该设置配置为 `true`, 否则为 `false` |
| GOOGLE_ANALYTICS_ID | 如果你打开了 Google Analytics，你必须设置 Google Analytics ID，否则无法记录网站浏览记录信息 |
| APPLICATION_NAME | 设置站点的名字 |
| TIMEZONE | 设置站点的时区 |
| LOCALE | 设置整个站点语言显示，暂时只有 `en/zh_cn` 两个选项，如需添加新的语言，可通过 `resource\lang` 设置新的语言 |
| MAIL_FROM | 邮件发送地址 |
| MAIL_NAME | 邮件发件人 |
| GITHUB_CLIENT_ID | Github Client ID, 如果该站点可以通过 Github 进行注册登录，请填写此参数 |
| GITHUB_CLIENT_SECRET | Github Clicent Secret, 如果该站点可以通过 Github 进行注册登录，请填写此参数 |
| GITHUB_REDIRECT | Github Clicent Redirect, 如果该站点可以通过 Github 进行注册登录，请填写此参数 |
| YOUDAO_API_KEY | Youdao api key，如果你需要使用有道 API 去将文章标题翻译为 可读性更好的 Slug 则设置此参数 |
| YOUDAO_KEY_FROM | Youdao key form，同上 |
| UPYUN_BUCKET | 又拍云服务名字 |
| UPYUN_OPERATOR | 又拍云操作员的名字 |
| UPYUN_PASSWORD | 又拍云操作员的密码 |
| UPYUN_DOMAIN | 又拍云服务分配的域名 |
| UPYUN_PROTOCOL | 又拍云服务使用的协议，如 https、http |

> 如果你想改变博客基本信息以及一些文本的显示，你可以编辑 `config/blog.php` 文件，设置你想要的配置。
