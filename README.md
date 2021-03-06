# **Video Metadata & Thumbnails**

[![Latest Version on NPM](https://img.shields.io/npm/v/video-metadata-thumbnails.svg?style=flat-square)](https://npmjs.com/package/video-metadata-thumbnails)
[![Download Count](https://img.shields.io/npm/dt/video-metadata-thumbnails.svg)](https://www.npmjs.com/package/video-metadata-thumbnails)
[![issue](https://img.shields.io/badge/bug-issue-red.svg)](https://github.com/wangweiwei/video-metadata-thumbnails/issues)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/wangweiwei/video-metadata-thumbnails/blob/master/LICENSE)
[![Dependency Status](https://david-dm.org/wangweiwei/video-metadata-thumbnails.svg)](https://david-dm.org/wangweiwei/video-metadata-thumbnails)
[![devDependency Status](https://david-dm.org/wangweiwei/video-metadata-thumbnails/dev-status.svg)](https://david-dm.org/wangweiwei/video-metadata-thumbnails?type=dev)

Convenience method(or Video object) to get metadata and thumbnails of HTML5 video or audio(only metadata) Blob.

English | [简体中文](https://github.com/wangweiwei/video-metadata-thumbnails/blob/master/README.zh.md)

## **Installation**

```shell
npm install --save video-metadata-thumbnails
```

or

```
yarn add video-metadata-thumbnails
```

## **Usage**

### getMetadata method &  getThumbnails method

​	Add `video-metadata-thumbnails.iife.js` to your document and get the metadata or thumbnails value of the promise returned by `then`:

```html
<input type="file" onchange="onChange(this.files)" />
<script src="your cdn path/video-metadata-thumbnails.iife.js"></script>
<script>
function onChange(files) {
  __video_metadata_thumbnails__.getMetadata(files[0]).then(function(metadata) {
    console.log('Metadata: ', metadata);
  })
  __video_metadata_thumbnails__.getThumbnails(files[0]).then(function(thumbnails) {
    console.log('Thumbnails: ', thumbnails);
  })
}
</script>
```

​	Alternatively, you can import(or require) `video-metadata-thumbnails` by getting it from `npm` :

```javascript
import { getMetadata, getThumbnails } from 'video-metadata-thumbnails';
  
const metadata = await getMetadata(blob);
const thumbnails = await getThumbnails(blob, {
  quality: 0.6
});
console.log('Metadata: ', metadata);
console.log('Thumbnails: ', thumbnails);
```
### Video Object

​	Import(or require) `video-metadata-thumbnails` by getting it from `npm`

```      javascript
import { Video } from 'video-metadata-thumbnails';

const video = new Video(blob);
console.log('Metadata:', await video.getMetadata());
console.log('Thumbnails:', await video.getThumbnails({
  quality: 0.6
}))
```

## **Thumbnails' Options**

* quality
  * type: number
  * default: 0.7
  * description: video thumbnails' quality
* interval
  * type: number
  * default: 1
  * description: time interval
* scale
  * type: number
  * default: 0.7
  * description: video thumbnails' scale
* start
  * type: number
  * default: 0
  * description: start frame
* end
  * type: number
  * default: 0
  * description: the end of frame

## **Example**

[![Software License](https://img.shields.io/badge/clicke-me-red.svg)](https://www.ellow.cn/examples/video-metadata-thumbnails/index.html)

## **⚠️  Notice**

​	`Blob` object is required in browser.


## **License**
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://github.com/wangweiwei/video-metadata-thumbnails/blob/master/LICENSE)

Copyright (c) 2020-present, Weiwei Wang 
