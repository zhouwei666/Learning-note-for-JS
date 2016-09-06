#JS的一些学习笔记
<a href="#filterUsing">（一）filter()函数的用法</a>
***
##filter()函数
<div id="filterUsing">
<h3>filter()基本语法：</h3>
<pre>
  <code>arr.filter(callback[, thisArg]</code>
</pre>
<p>
filter为数组中的每个元素调用一次 callback 函数，并利用所有使得callback返回true或等价于true 的值的元素创建一个新数组。
callback只会在已经赋值的索引上被调用，对于那些已经被删除或者从未被赋值的索引不会被调用。
那些没有通过 callback 测试的元素会被跳过，不会被包含在新数组中。<strong>注意：filter不会改变原数组</strong>
</p>
<h3>callback()参数说明：</h3>
<p>
callback 被调用时传入三个参数：
  <ol><li>元素的值
  </li><li> 元素的索引
  </li><li>被遍历的数组
  </li></ol>
</p>
<p>
如果为 filter 提供一个 thisArg 参数，则它会被作为 callback 被调用时的 this 值。否则，callback 的this 值在非严格模式下将是全局对象，严格模式下为 undefined。
</p>
<h3>filter实例：</h3>
<pre>
<code>
function isBigEnough(element) {
  return element >= 10;
}
var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);
// filtered is [12, 130, 44]
document.write(filtered);
</code>
</pre>
</div>
