## Chrome 插件

###替换照片插件插件实例

1、配置manifest.json文件：
```js
{
  // 固定值2
  "manifest_version": 2,

  "name": "fjy-wipeImg",
  "description": "去除网页img",
  "version": "1.0",

  "browser_action": {

  },
  // 网页许可
  "permissions": [
  	"http://*/*", // 可以通过executeScript或者insertCSS访问的网站
    "https://*/*" // 可以通过executeScript或者insertCSS访问的网站
  ],
  // 直接在这里配置js文件
  "content_scripts": [{
    "matches": ["<all_urls>"],
    "js": ["jquery-3-3.1.js", "content_action.js"]
  }]
  
}
```
如需其他参数，请查看参考文献

2、根据自身需要配置功能js文件，如：content_action.js
```js
setTimeout(function(){
	$('img').map(function(idex,item){$(item).attr('src','')})
},3000)

```

####参考文献
 - [【干货】Chrome插件(扩展)开发全攻略](http://www.cnblogs.com/liuxianan/p/chrome-plugin-develop.html)
	* [demo](https://github.com/sxei/chrome-plugin-demo)
 - [Chrome扩展及应用开发（首发版）](http://www.ituring.com.cn/book/1421)
 - [Chrome360翻译文档](http://open.chrome.360.cn/extension_dev/overview.html)
