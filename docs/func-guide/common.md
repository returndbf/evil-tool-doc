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
 * @param {number} delay - 等待时间 
 * @param {any} resolveInfo - Promise resolve的参数
 * @return {Promise<any>} resolveInfo
 */ 
async wait(delay=1000,resolveInfo)

```


### urlSearch 
#### 解析url的search参数
```js
import {urlSearch} from "evil-tool"
/**
 * @param {string | undefined}  url - 浏览器环境中为空则自动获取当前url，nodejs为空则抛出异常
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

### generateRandomString 
#### 生成随机字符串
```js
import {generateRandomString} from "evil-tool"
/**
 * @param {number} length  - 随机字符串长度
 * @return {string} 返回随机字符串
 */ 
generateRandomString(length = 8)
```
### getType
#### 获取变量类型
```js
import {getType} from "evil-tool"
/**
 * @param {any} value -  获取类型的数据
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
 * @param {string} fileName - 文件名，不要带后缀
 * @return {Promise<{content:string,file:File}>} - Promise对象,content为图片的base64，file为图片文件
 */
async convertBlobToFile(blob, fileName = "file")
``` 


### fetchImageAsBlob
#### 获取图片的Blob对象
```js
import {fetchImageAsBlob} from "evil-tool"
/**
 * @param {string} url - 图片地址
 * @return {Promise<Blob>} - resolve为Blob对象
 */
async fetchImageAsBlob(url)
``` 

### excel2Csv
#### 将Excel文件转换为Csv文件
```js
import {excel2Csv} from "evil-tool"
/**
 * @params {ArrayBuffer} arraybuffer - excel文件流
 * @return {Blob} -  返回的blob对象
 * 
 */
 excel2Csv(arraybuffer)
```
 
 ### excel2Json
 #### 将Excel文件转换为js对象数据

 ```js
 import {excel2Json} from "evil-tool"
 /**
  * @params {ArrayBuffer} arraybuffer - excel文件流
  * @params {string[]} omitKeys - 忽略的列名
  * @return {object[]}  - 返回的js对象数组
  */
 excel2Json(arraybuffer,omitKeys)
 ```
 ### excel2Txt
 #### 将Excel文件转换为txt文件
 ```js
 import {excel2Txt} from "evil-tool"
 /**
  * @params {ArrayBuffer} arraybuffer - excel文件流
  * @params {string[]} omitKeys - 忽略的列名
  * @params {string} splitSymbol - 每个文本的分隔符
  * @return {Blob} - 返回的blob对象
  */
 excel2Txt(arrayBuffer,omitKeys=[],splitSymbol = ',')
 ``` 

 ### excel2Word
 #### 将Excel文件转换为word文件，形式为表格
 ```js
 import {excel2Word} from "evil-tool"
 /**
  * @params {ArrayBuffer} arraybuffer - excel文件流
  * @params {string[]} omitKeys - 忽略的列名
  * 
  * @return {Promise<Blob>} - 返回的blob对象
  */
 async excel2Word(arrayBuffer,omitKeys=[])
 ``` 