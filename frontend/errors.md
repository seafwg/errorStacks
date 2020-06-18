# 问题集合：

## 1. ueditor 是如何把 mini 组件库识别的，两者是怎么结合使用的

## 2. 自己设想使用利用 html5 的 contenteditable='true'容器可编辑属性，添加的容器中 js,css 失效问题

## 3. 自己 antd vue 开发中如何与 ueditor 关联，两者结合使用

## 4. 关于 html 标签转换成 json 对象，json 对象转换成 html 元素之间的互转，

```ts
// himalaya库转换  cnpm/npm i himalaya -D [或者script:scr引入]
let json = parse(html) // 将html元素转换成json对象
// html转换成json对象后可进一步操作：
removeWhitespace(json)
let html1 = stringify(json) // 将html转换后的json转换成html元素
```

```ts
// 移除空格
const removeEmptyNodes = (nodes) => {
	return nodes.filter((node) => {
		if (node.type === 'element') {
			node.children = removeEmptyNodes(node.children)
			return true
		}
		return node.content.length
	})
}
//过滤掉多余的空格
const stripWhitespace = (nodes) => {
	return nodes.map((node) => {
		if (node.type === 'element') {
			node.children = stripWhitespace(node.children)
		} else {
			node.content = node.content.trim()
		}
		return node
	})
}

// 删除多余的空格
export const removeWhitespace = (nodes) => {
	return removeEmptyNodes(stripWhitespace(nodes))
}
```

## 5.VScode 运行 javaweb 项目前端热跟新问题

## 6.急需解决的问题：老的项目中是否支持 es6 的语法，原声 js,jq DOM 操作的区别：

## 7.ideal 中 java 项目的出错，tomact 编译一段时间一直卡顿

原因：

```properties
jms.ip=127.0.0.1
jms.port=62222
jms.dir=D:\\jms   #项目中的路径问题

#jms.dir=E:\\jms   ## √ 一般人的电脑没有D盘
```

## 8.mini ui 中 js 动态修改单元格的属性

## 9，数组中的 list 分组

```javascript
// 创建模板list
function createList(data) {
	var isOdd = data.length % 2 == 0 ? true : false
	for (var i = 0; i < data.length; i++) {
		var n = 2 * i
		if (n >= data.length) {
			return
		}
		if (i <= n) {
			var oTr = $("<tr class='tr_form'></tr>")
			var m = 2 // 最后一个为奇数的时候只渲染一个
			if (n == data.length - 1 && !isOdd) {
				m = 1
			}
			for (var j = 0; j < m; j++) {
				// 控制列
				var oTd =
					'<td>' +
					data[n + j].title +
					'</td>' +
					'<td><input id=' +
					data[n + j].id +
					' name=' +
					data[n + j].name +
					" class='mini-datepicker' style='width: 100%' /></td>"
				console.log(oTr)
				oTr.append(oTd)
			}
		}
		$('#billsTmp').append(oTr)
	}
}
```

**等价于**

```javascript
function createList(data) {
	var isOdd = data.length % 2 == 0 ? true : false
	for (var i = 0; i < data.length; i++) {
		var n = 2 * i
		if (n >= data.length) {
			return
		}
		if (i <= n) {
			var oTr = $('<tr></tr>')
			if (n == data.length - 1 && !isOdd) {
				var oTd =
					'<td>' +
					data[n].title +
					'</td>' +
					'<td><input id=' +
					data[n].id +
					' name=' +
					data[n].name +
					" class='mini-datepicker' style='width: 100%' /></td>"
				oTr.append(oTd)
			} else {
				var oTd =
					'<td>' +
					data[n].title +
					'</td>' +
					'<td><input id=' +
					data[n].id +
					' name=' +
					data[n].name +
					" class='mini-datepicker' style='width: 100%' /></td>" +
					'<td>' +
					data[n + 1].title +
					'</td>' +
					'<td><input id=' +
					data[n + 1].id +
					' name=' +
					data[n + 1].name +
					" class='mini-textbox' style='width: 100%' /></td>"
				oTr.append(oTd)
			}
		}
		$('#billsTmp').append(oTr)
	}
}
```

## 10.发送get请求时，url中解析出现乱码的解决，无法跳转

**使用encodeURI()和encodeURIComponent()函数将字符串转换为通用资源标识符**

**前提是字符串：**

```ts
var uri="http://www.jxbh.cn/illegal value.htm#start";
console.log(encodeURI(uri));
// http://www.jxbh.cn/illegal%20value.htm#start
var uri="http://www.jxbh.cn/illegal value.htm#start";
console.log(encodeURIComponent(uri));
// http%3A%2F%2Fwww.jxbh.cn%2Fillegal%20value.htm%23start
```

**decodeURI()和decodeURIComponent()函数可实现之间的转化**

## 11.数据机构的整合：[x,y],[1,2] => {x:1,y:2}

```js
var temp1 = ['x','y','z'];
var temp2 = [1,2,3];
var obj = {};
for(let i = 0;i < temp1.length;i++) {
	obj[temp1[i]] = temp2[i];
}
console.log(obj);
// {x: 1, y: 2, z: 3}
```

