# video-tn-blob
生成视频的帧动画

## 使用方法
mnpm上安装模块之后
```js

function onChange(files) {
  __video_metadata_thumbnails__.getMetadata(files[0]).then(function(metadata) {
    console.log('Metadata: ', metadata);
  })
  __video_metadata_thumbnails__.getThumbnails(files[0]).then(function(thumbnails) {
    console.log('Thumbnails: ', thumbnails);
  })
}

```
### 通过Video对象

​	通过导入`Video`来自行初始化视频对象，然后通过`getMetadata`和`getThumbnails`获取元数据和帧缩略图：

```      javascript
import { Video } from '@dp/video-tn-blob';

const video = new Video(blob);
console.log('Metadata:', await video.getMetadata());
console.log('Thumbnails:', await video.getThumbnails({
  quality: 0.6
}))
```

## **缩略图选项**

* quality
  * 类型: number
  * 默认值: 0.7
  * 描述: 视频缩略图的质量
* interval
  * 类型: number
  * 默认值: 1
  * 描述: 获取帧图片的时间间隔
* scale
  * 类型: number
  * 默认值: 0.7
  * 描述: 帧图片的缩放值
* start
  * 类型: number
  * 默认值: 0
  * 描述: 获取帧图片的起始帧
* end
  * 类型: number
  * 默认值: 0
  * 描述: 获取帧图片的终止帧

