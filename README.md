MicroTmpl 微型模板
=========

Super Micro JavaScript Template Engine
超微型前端模板

## Brief Introduction 简介

The only advantage is that this template engine is super micro, just about 15 lines. 
唯一的优点就是超微型，只有15行左右的代码

### Features 特性

- No logic 无逻辑
- Automatic loop for Arrays 数组自动遍历
- No JavaScript Runtime 不支持模板中的JavaScript代码

## Usage 用法

See we have a template string like this：
假设我们有如下模板：

	var tmplStr = '<li>My Name is {%name%}, I\'m {%age%} years old.</li>';

And an Array, an Object:
以及一个数组，一个对象：

	//Array 数组
	var arr = [{
		name:'TooBug',
		age:18
	},{
		name:'ThreeBug',
		age:18.1
	}];

	//Object 对象
	var obj = {
		name:'Another TooBug',
		age:18.2
	};

Render like this:
这样渲染：

	var html1 = MicroTmpl(tmplStr,arr);
	// <li>My Name is TooBug, I\'m 18 years old.</li><li>My Name is ThreeBug, I\'m 18.1 years old.</li>

	var html2 = MicroTmpl(tmplStr,obj);
	// <li>My Name is Another TooBug, I\'m 18.2 years old.</li>

## Addtions 其它

Depend on Array.forEach of ES5, so if used in the browsers that is not so modern, you will need a polyfill.
依赖ES5中的Array.forEach，所以如果用在不是那么新的浏览器上，需要一个ES5数组补丁。

Since the performance is not so well, it only suit for little projects.(Which maybe the JS code is smaller than a template engine.)
由于这个模板的性能不是那么好，所以它只适合比较小的项目。（比如项目的JS代码本身比模板引擎还要小的。）
