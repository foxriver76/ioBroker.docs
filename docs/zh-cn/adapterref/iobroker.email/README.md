---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.email/README.md
title: TR: ioBroker email
hash: mGpv2SOd2J5VYHrF3xxx5reEDja3CX4LhnpHoG0jI7w=
---
![TR: Logo](../../../en/adapterref/iobroker.email/admin/email.png)

![TR: Number of Installations](http://iobroker.live/badges/email-stable.svg)
![TR: NPM version](http://img.shields.io/npm/v/iobroker.email.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.email.svg)

TR: # ioBroker email
TR: ![TR: Test and Release](https://github.com/ioBroker/ioBroker.email/workflows/Test%20and%20Release/badge.svg) [![TR: Translation status](https://weblate.iobroker.net/widgets/adapters/-/email/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

TR: Send emails from ioBroker.

TR: The adapter uses [TR: nodemailer](https://github.com/nodemailer/nodemailer) to provide the functionality.

TR: **This Adapter requires nodejs 6.x or higher!!**

TR: **This adapter uses Sentry libraries to automatically report exceptions and code errors to the developers.** For more details and for information how to disable the error reporting see [TR: Sentry-Plugin Documentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry reporting is used starting with js-controller 3.0.

TR: To use Gmail you may need to configure "Allow Less Secure Apps" in your Gmail account unless you are using 2FA in which case you would have to create an Application Specific password. You also may need to unlock your account with "Allow access to your Google account" to use SMTP.

TR: ## Usage
TR: To send email from ScriptEngine just write:

```
// send email to all instances of email adapter
sendTo("email", "Email body");

// send email to specific instance of email adapter
sendTo("email.1", "Email body");

// To specify subject or other options
sendTo("email", {
    from:    "iobroker@mydomain.com",
    to:      "aabbcc@gmail.com, xxyyzz@gmail.com", // comma separated multiple recipients.
    subject: "Message from ioBroker",
    text:    "This is test email to you!"
});

// To send attachments
sendTo("email", {
    attachments: [
       // use file on disk as attachment
       {path: "/pathToImage/picture1.jpg"},
       {   // use URL as an attachment
            filename: 'license.txt',
            path: 'https://raw.github.com/andris9/Nodemailer/master/LICENSE'
       }
    ]
});

// To send in html format
sendTo("email", {
    html: "<p>Embedded image: <img src='cid:image1'/></p>",
    attachments:[
        {path: "path/to/file/image1.jpg", cid: "image1"}
    ]
});
```

TR: To send email from other adapter use **adapter.sendTo** function.

TR: ## Supported services
TR: - 1und1
TR: - AOL
TR: - DebugMail.io
TR: - DynectEmail
TR: - FastMail
TR: - GandiMail
TR: - Gmail
TR: - Godaddy
TR: - GodaddyAsia
TR: - GodaddyEurope
TR: - hot.ee
TR: - Hotmail
TR: - iCloud
TR: - ith
TR: - mail.ee
TR: - Mail.ru
TR: - Mailgun
TR: - Mailjet
TR: - Mandrill
TR: - Naver
TR: - Office365
TR: - OpenMailBox
TR: - Postmark
TR: - QQ
TR: - QQex
TR: - SendCloud
TR: - SendGrid
TR: - SES
TR: - SES-US-EAST-1
TR: - SES-US-WEST-2
TR: - SES-EU-WEST-1
TR: - Sparkpost
TR: - Yahoo
TR: - Yandex
TR: - Zoho
TR: - User specific (Server, port and security defined manually)

TR: For other services see documentation of **Nodemailer**: `§§LLLLL_0§§`

## Changelog

### 1.0.10 (2021-07-06)
* (Apollon77) Optimize for js-controller 3.3

### 1.0.9 (2021-02-22)
* (Apollon77) Call message callback always with error or without

### 1.0.7 (2020-06-11)
* (Apollon77) Make sure adapter is not crashing on stop in some edge cases
* (Apollon77) Add Sentry for crash reporting with js-controller >=3.x

### 1.0.6 (2019-12-29)
* (bluefox) Compact mode supported

### 1.0.5 (2019-09-18)
* (Apollon77/bluefox) js-controller 2.0 compatibility, dependency updates

### 1.0.4 (2018-03-26)
* (skraw.iobroker) Add ith

### 1.0.3 (2018-03-04)
* (bluefox) fix blockly
* (bluefox) Admin3 ready

### 1.0.2 (2017-01-31)
* (instalator) fix translations

### 1.0.1 (2016-12-20)
* (bluefox) add Office365

### 1.0.0 (2016-10-12)
* (bluefox) support of blockly

### 0.2.1 (2016-09-03)
* (bluefox) fix sending emails after first one

### 0.2.0 (2016-08-29)
* (bluefox) filter out double messages
* (bluefox) use new nodemailer packet

### 0.1.2 (2015-04-30)
* (bluefox) fix settings if "user defined" was selected

### 0.1.1 (2015-04-28)
* (bluefox) update configuration page and decode errors

### 0.1.0 (2015-01-02)
* (bluefox) prepare npm

### 0.0.4 (2014-11-2)
(bluefox) support of new naming concept

### 0.0.3 (2014-10-09)
* (bluefox) support of daemon mode
* (bluefox) add Gruntfile.js

## License

The MIT License (MIT)

Copyright (c) 2014-2021 bluefox

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.