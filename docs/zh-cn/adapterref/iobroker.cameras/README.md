---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.cameras/README.md
title: TR: ioBroker.cameras
hash: md4NOTpy9bBQKDCixUgrVhRjR4M6ZCwAR29la883rHo=
---
![TR: Logo](../../../en/adapterref/iobroker.cameras/admin/cameras.png)

![TR: NPM version](http://img.shields.io/npm/v/iobroker.cameras.svg)
![TR: Downloads](https://img.shields.io/npm/dm/iobroker.cameras.svg)
![TR: Dependency Status](https://img.shields.io/david/ioBroker/iobroker.cameras.svg)
![TR: Known Vulnerabilities](https://snyk.io/test/github/ioBroker/ioBroker.cameras/badge.svg)
![TR: NPM](https://nodei.co/npm/iobroker.cameras.png?downloads=true)
![TR: Travis-CI](http://img.shields.io/travis/ioBroker/ioBroker.cameras/master.svg)

TR: # ioBroker.cameras
TR: ## IP-Cameras adapter for ioBroker
TR: You can integrate you web/ip cameras into vis and other visualisations.
If you configure a camera with name `cam1` it will be available on web server under `http(s)://iobroker-IP:8082/cameras.0/cam1`.

TR: Additionally, you the image could be requested via message:

```
sendTo('cameras.0', 'image', {
    name: 'cam1',
    width: 100, // optional
    height: 50, // optional
    angle: 90   // optional
}, result => {
    const img = 'data:' + result.contentType + ';base64,' + result.data;
    console.log('Show image: ' + img);
});
```

TR: The result is always in `jpg` format.

TR: Supported cameras:

TR: ### URL image This is normal URL request, where all parameters are in URL. Like `http://mycam/snapshot.jpg`
TR: ### URL image with basic authentication
TR: This is URL request for image, where all parameters are in URL, but you can provide the credentials for basic authentication. Like `http://mycam/snapshot.jpg`

TR: <!-- Placeholder for the next version (at the beginning of the line):

TR: ### __WORK IN PROGRESS__ -->

## Changelog
### 0.1.4 (2021-07-13)
* (bluefox) Add role for states

### 0.1.3 (2020-08-08)
* (Hirsch-DE) Parameters were applied

### 0.1.2 (2020-06-03)
* (bluefox) implemented get image by message

### 0.1.0
* (bluefox) URL and URL with basic authentication were implemented

### 0.0.1
* (bluefox) initial release

## License
MIT License

Copyright (c) 2020-2021 bluefox <dogafox@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.