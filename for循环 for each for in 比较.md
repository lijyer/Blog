**for：遍历数组**

//对象数组
var  arr = [
		{Monday: '星期一', Tuesday: '星期二', Wednesday: '星期三'}
	]
for (var i=0; i<arr.length;i++){ // i是下标（索引）
	console.log(i)
	console.log(arr[i])

}

结果:

0

{Monday: "星期一", Tuesday: "星期二", Wednesday: "星期三"}

*//数组*
var arr = ["星期一","星期二","星期三"]
for (var j=0; j<arr.length;j++){*// j是下标（索引）*
console.log(j)
console.log(arr[j])
}

结果:

0

星期一

1

星期二

2

星期三

**forEach：遍历数组，但不能使用break、continue和return语句**

//对象数组
var  arr = [
		{guangzhou: '广州', shanghai: '上海', beijing: '北京'},
		{Monday: '星期一', Tuesday: '星期二', Wednesday: '星期三'}
	]
arr.forEach(function(value,index){ //第一个参数是值，第二个参数是下标（索引）
	console.log(value)
	console.log(index)

}

结果: 

{guangzhou: "广州", shanghai: "上海", beijing: "北京"},

0

{Monday: "'星期一", Tuesday: "星期二" Wednesday: "星期三"}

1

*//数组*
var arr = ["星期一","星期二","星期三"];
arr.forEach(function(value,index){*//第一个参数是值，第二个参数是下标（索引）*
console.log(value)
console.log(index)
})

结果:

星期一

0

星期二

1

星期三

2

**for…in**：**遍历数组索引、对象的属性**
**使用for…in遍历时，原型链上的所有属性都将被访问**
例如：

var arr = ["星期一","星期二","星期三"];
Array.prototype.something = ["放假","休息咯"];
for (var i in arr){ *// i是下标（索引）*
console.log(arr[i])
}

结果:

星期一

星期二

星期三

（2）["放假","休息咯"]



//对象
var obj = {guangzhou: '广州', shanghai: '上海', beijing: '北京'}
Object.prototype.something2={shenzhen:'深圳'}
for (var i in obj){ 
	console.log(obj[i])

}

结果:

广州

上海

北京

{shenzhen:'深圳'}