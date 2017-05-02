
##字符串转数字

使用内置函数转化

```
var s = "123456";
return Number(s);
return parseInt(s);
return parseFloat(s);

```

使用乘法、除法运算转换

```
var s = "123456";
return s * 1;
return s / 1;

```

使用数组思路，自定义函数转化

```
var s = '123456';
return s.split("").map(function(x){
	return x * 1;
}).reduce(function(x, y) {
	return x * 10 + y;
});

```

在上面基础上，如果字符串中有英文字符时，剔除英文字符，只要数字：

```
var s = "123ab456"
return s.split("").filter(function(x){
	return x * 1;
}).map(function(x){
	return x * 1;
}).reduce(function(x, y) {
	return x * 10 + y;
})

//结果 123456 

```