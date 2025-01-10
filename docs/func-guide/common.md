---
title: 浏览器和Nodejs通用函数
order: 2
nav:
  title: 指南
---

<div style="text-align: center; font-size: xx-large;font-weight: bolder">浏览器和Nodejs通用函数</div> 

### wait
#### 让程序同步等待一段时间
```js
import {wait} from "evil-tool"
/**
 * @param {number} 等待时间 
 * @param {any} resolveInfo Promise resolve的参数
 * @return {Promise<any>} resolveInfo
 */ 
async wait(delay=1000,resolveInfo)

```


### urlSearch 
#### 解析url的search参数
```js
import {urlSearch} from "evil-tool"
/**
 * @param {string | undefined} url，浏览器环境中为空则自动获取当前url，nodejs为空则抛出异常
 * @return {{getProperty:(key:string)=>string,getAllProperty:()=>{[key:string]:string},instance:URLSearchParams}}
 */
urlSearch(url = undefined)
useage: urlSearch("https://www.baidu.com/s?ie=UTF-8").getProperty("ie")
```


### clearConsole 
#### 清空控制台
```js
import {clearConsole} from "evil-tool"
/** 
 * @return {void}
 */
clearConsole()
```

### getRandomString 
#### 生成随机字符串
```js
import {getRandomString} from "evil-tool"
/**
 * @param {number} length 随机字符串长度
 * @return {string} 返回随机字符串
 */ 
getRandomString(length = 8)
```
### getType
#### 获取变量类型
```js
import {getType} from "evil-tool"
/**
 * @param {any} 获取类型的字符串
 * @return {string} 返回类型,结果为各个类型的构造函数的名字，例如'Number'
 */
getType(value)
``` 

### convertBlobToFile
#### 将Blob对象转换为File对象
```js
import {convertBlobToFile} from "evil-tool"
/**
 * @param {Blob} blob 
 * @param {string} fileName 文件名，不要带后缀
 * @return {Promise<{content:string,file:File}>} - Promise对象,content为图片的base64，file为图片文件
 */
async convertBlobToFile(blob, fileName = "file")
``` 


### fetchImageAsBlob
#### 获取图片的Blob对象
```js
import {fetchImageAsBlob} from "evil-tool"
/**
 * @param {string} url 图片地址
 * @return {Promise<Blob>} - resolve为Blob对象
 */
async fetchImageAsBlob(url)
``` 