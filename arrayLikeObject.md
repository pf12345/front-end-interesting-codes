
##类数组

####定义：

1.拥有length属性，其它属性（索引）为非负整数(对象中的索引会被当做字符串来处理，这里你可以当做是个非负整数串来理解)

2.不具有数组所具有的方法

示例：

```
var arrLike = {0: "name", 1: "address", 2: "age", length: 3};

```

####类数组判断：

```
function isArrayLike(o) {
    if (o && typeof o === 'object' && 
        isFinite(o.length) && o.length >= 0 && 
        o.length===Math.floor(o.length) && 
        o.length < 4294967296) {
           return true; 
        }                  
    else {
      return false;
    }
}

```

####类数组转化数组：

使用 Array.prototype.slice.call() 方法:

```
var arrLike = {0: "name", 1: "address", 2: "age", length: 3};
Array.prototype.slice.call(arrLike);

//["name", "address", "age"]

```