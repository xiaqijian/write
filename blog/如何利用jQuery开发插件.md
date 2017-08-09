我们在使用jQuery的时候，我们都经常有直接去下载人家的插件，其实我们可以自己去开发

> 注，本文使用最新本jQuery API

## 1.0jQuery开发插件有几种

jQuery开发插件有这么三种方法
```
 1. 利用$.extend()
 2. 利用$.fn.extend()
 3. 利用 $.widget();
```
> 需求，我们开发一个选择一个元素，变色

### 1.1 $.extend()
```javascript
$.extend({
    sayHello: function(name) {
        console.log('Hello,' + (name ? name : 'Dude') + '!');
    }
})
$.sayHello(); //调用
$.sayHello('Wayou'); //带参调用
```
这种方法直接利用`$.方法名称`就可以进行调用了

### 1.2 $.fn.extend()

```
$.fn.extend({
			myPlugin:function(options) {
			    var defaults = {
			        'color': 'red',
			        'fontSize': '12px'
			    };
			    var settings = $.extend({}, defaults, options);
			    return this.css({
			        'color': settings.color,
			        'fontSize': settings.fontSize
			    });
			}
		})
```
html:
```
$('p').myPlugin({
			'color': '#efefef',
			'fontSize': '20px'
		});
```
## 2.0 最好将代码写在这个里面
```
;(function($, window, document,undefined) {
	// you code
})(jQuery, window, document);
```
