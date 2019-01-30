
1.let 和 const
1.let 和 const
块级作用域；
无变量提升；
暂时性死区；
不允许重复声明；
let和const声明的变量只在它所在的代码块有效。
{
    let a = 10;
    var b = 1;
}
console.log(a); // ReferenceError: a is not defined.
console.log(b); // 1

for循环还有一个特别之处，就是设置循环变量的那部分是一个父作用域，而循环体内部是一个单独的子作用域。
for (let i = 0; i < 3; i++) {
  let i = 'abc';
  console.log(i);
}
// abc
// abc
// abc

暂时性死区
ES6 明确规定，如果区块中存在let和const命令，这个区块对这些命令声明的变量，从一开始就形成了封闭作用域。凡是在声明之前就使用这些变量，就会报错。
if (true) {
  // TDZ开始
  tmp = 'abc'; // ReferenceError
  console.log(tmp); // ReferenceError
  let tmp; // TDZ结束
  console.log(tmp); // undefined
  tmp = 123;
  console.log(tmp); // 123
}

不允许重复声明
let不允许在相同作用域内，重复声明同一个变量。
// 报错
function func() {
  let a = 10;
  var a = 1;
}

// 报错
function func() {
  let a = 10;
  let a = 1;
}


const 命令
const声明一个只读的常量。一旦声明，常量的值就不能改变。
const一旦声明变量，就必须立即初始化，不能留到以后赋值。
const的作用域与let命令相同：只在声明所在的块级作用域内有效。







