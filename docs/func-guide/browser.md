---
title: 浏览器专用函数
order: 1
nav:
  title: 指南
---

<div style="text-align: center; font-size: xx-large;font-weight: bolder">浏览器专用函数</div> 

### editDocument

#### 设置页面文档为可编辑
```js
import {editDocument} from "evil-tool"
/**
 *  @return {void}
 */
editDocument()

```


### pasteImage

#### 监听dom对象绑定的快捷键，使用快捷键获取剪切板的图片数据，默认快捷键为ctrl+v
#### 支持传入回调函数以及Promise
```js
import {pasteImage} from "evil-tool"
/**
 * @param {HtmlDom} domTarget - 绑定对象
 * @param {()=>{content:string,file:File})} cb - 回调函数，会传入结果对象,content为图片的base64，file为图片文件
 * @param {string} key1 - 第一个快捷键
 * @param {string} key2 - 第二个快捷键
 * @return {Promise<{content:string,file:File}>} - Promise对象,content为图片的base64，file为图片文件
 */
pasteImage(domTarget, cb = null, key1 = 'ctrlKey', key2 = 'v')

```


### CusLog 
#### 格式化的console.log
```js
import {CusLog} from "evil-tool"
/**
 * 格式化的console.log
 */
class CusLog {
    /**
     * @param {string} content - 输出内容
     */ 
   static info(message)

   static error(message)

   static warn(message)

   static pink(message)
}

useage: CusLog.info('hello world')
```

### downloadBlob 
#### 下载blob文件

```js
import {downloadBlob} from "evil-tool"
/**
 * @param {Blob} blob - blob对象
 * @param {string} filename - 文件名，需要后缀
 */
downloadBlob(blob, filename)
``` 