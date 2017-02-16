# Config

The default language is english. If you want to change to chinese, you can add the `LOCALE` to the `.env` file:

```php
LOCALE=zh_cn #options: en/zh_cn
```

## The configuration's list for the `.env`:

| Key | Description |
| --- | --- |
| MAIL_NOTIFICATION | Whether to open the mail notification to send (open need to set the mail driver), the default is `false`, open is set to` true` |
| DEFAULT_AVATAR | Set the default avatar for the site |
| DEFAULT_ICON | Set the favicon for the site |
| ARTICLE_SHARE | If you want to open the social share for the article, you can set `true` for the config. Otherwise, you should set it `false` |
| DISCUSSION_SHARE | If you want to open the social share for the discussion, you can set `true` for the config. Otherwise, you should set it `false` |
| SOCIAL_SHARE_SITES | Set the ways for social share |
| SOCIAL_SHARE_MOBILE_SITES | Set the ways for social share in mobile |
| GOOGLE_OPEN | If you want to open the google analytics, you should set the config `true` |
| GOOGLE_ANALYTICS_ID | If you open the google analytics, you must set the google analytics id |
| APPLICATION_NAME | Set your application name for the site |
| TIMEZONE | Set the application timezone for the site |
| LOCALE | Set the application language for the site |
| MAIL_FROM | Email From Address |
| MAIL_NAME | Email From Name |
| GITHUB_CLIENT_ID | Github Clicent ID |
| GITHUB_CLIENT_SECRET | Github Clicent Secret |
| GITHUB_REDIRECT | Github Clicent Redirect |
| YOUDAO_API_KEY | Youdao api key used for the chinese article title to translate to the slug |
| YOUDAO_KEY_FROM | Youdao key form used for the chinese article title to translate to the slug |

> If you want to change the blog base information and some things to show, you can edit the `config/blog.php` file to set what you want.
