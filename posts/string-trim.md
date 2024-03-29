---
title: 过滤空格
date: 2019-10-24
---

过滤字符串中的空格是时常有的需求，过滤后可以得到更准确的输入结果。
<!-- more -->
下面是几种常见的过滤需求及实现方法：


## 过滤左边空格

```javascript
' 风萧萧兮易水寒'.trimStart()
// 或
' 风萧萧兮易水寒'.trimLeft()
```
`trimLeft()`方法是 `trimStart()` 方法的别名，所以它们所实现的效果一致。不过它们都是非标准化的方法，所以存在[兼容问题]，那不如自己动手呢：

```javascript
' 风萧萧兮易水寒 '.replace(/^\s*/g,'');
```

## 过滤右边空格

```javascript
'风萧萧兮易水寒 '.trimEnd()
// 或
'风萧萧兮易水寒 '.trimRight()
```
`trimRight()`方法则是 `trimEnd()` 方法的别名，所以它们所实现的效果也一致。它们也是非标准化方法，也存在[兼容问题]，还是要自己动手：

```javascript
" 风萧萧兮易水寒 ".replace(/\s*$/g,'');
```

## 过滤两边空格

```javascript
' 风萧萧兮易水寒 '.trim()
```
`trim()` 方法虽说是标准化方法，但是 IE9 以下还是不支持，不过自己动手也不是很难：

```javascript
" 风萧萧兮易水寒 ".replace(/(^\s*)|(\s*$)/g,'')
```


## 去除所有空格

去除所有空格没有原生的语法糖方法，正则名正言顺上位：

```javascript
" 风萧萧兮 易水寒 ".replace(/\s+/g,'')
```

## 总结
正则大法好~



[兼容问题]: https://caniuse.com/#search=trim