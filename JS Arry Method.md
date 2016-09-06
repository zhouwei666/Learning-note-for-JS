#JS的一些数组操作函数
<p><a href="#filterUsing">（一）filter()函数</a></p>
<p><a href="#sliceUsing">（二）slice()函数</a></p>
<p><a href="#concatUsing">（三）concat()函数</a></p>
<p><a href="#spliceUsing">（四）splice()函数</a></p>
***
<h2>filter()函数</h2>
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
<h2>slice()函数</h2>
<div id="sliceUsing">
<h3>定义和用法:</h3>
<p>slice() 方法返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。</p>
<p><strong>注意：该方法并不会修改数组，而是返回一个子数组。如果想删除数组中的一段元素，应该使用方法 Array.splice()。</strong></p>
<pre><code>
arrayObject.slice(start,end)
</code></pre>
<p>其中start是必需项，规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。end是可选项，规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。</p>
</div>
<h2>concat()函数</h2>
<div id="concatUsing">
<p>concat()方法用于连接两个或多个数组。<strong>该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。</strong></p>
<h3>语法</h3>
<pre><code>
arrayObject.concat(arrayX,arrayX,......,arrayX);
</code></pre>
<p>arrayX可以是具体的值，也可以是数组对象,可以是任意多个。该数组是通过把所有 arrayX 参数添加到 arrayObject 中生成的。如果要进行 concat() 操作的参数是数组，那么添加的是数组中的元素，而不是数组。</p>
</div>
<h2>splice()函数</h2>
<div id="spliceUsing">
<p>splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目。<strong>注意：该方法会改变原始数组</strong></p>
<h3>语法</h3>
<pre><code>
arrayObject.splice(index,howmany,item1,.....,itemX);
</code></pre>
<p>
其中index是必需项，整数，规定添加/删除项目的位置，如果是负数，则会加上数组的长度作为start的值；howmany必需，表示要删除的项目数量，如果设置为 0或者负数，则不会删除项目；<strong>item1,...itemX可选项，表示向数组对象中添加新的项目。</strong>
</p>
</div>
