#JS的一些数组操作函数
<p><a href="#filterUsing">（一）filter()函数</a></p>
<p><a href="#sliceUsing">（二）slice()函数</a></p>
<p><a href="#concatUsing">（三）concat()函数</a></p>
<p><a href="#spliceUsing">（四）splice()函数</a></p>
<p><a href="#mapUsing">（五）map()函数</a></p>
<p><a href="#applyUsing">（六）apply()、call()和bind()函数</a></p>
***
<h2 id="filterUsing">filter()函数</h2>
<div>
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
<h2 id="sliceUsing">slice()函数</h2>
<div>
<h3>定义和用法:</h3>
<p>slice() 方法返回一个新的数组，包含从 start 到 end （不包括该元素）的 arrayObject 中的元素。</p>
<p><strong>注意：该方法并不会修改数组，而是返回一个子数组。如果想删除数组中的一段元素，应该使用方法 Array.splice()。</strong></p>
<pre><code>
arrayObject.slice(start,end)
</code></pre>
<p>其中start是必需项，规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。end是可选项，规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。</p>
</div>
<h2 id="concatUsing">concat()函数</h2>
<div>
<p>concat()方法用于连接两个或多个数组。<strong>该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。</strong></p>
<h3>语法</h3>
<pre><code>
arrayObject.concat(arrayX,arrayX,......,arrayX);
</code></pre>
<p>arrayX可以是具体的值，也可以是数组对象,可以是任意多个。该数组是通过把所有 arrayX 参数添加到 arrayObject 中生成的。如果要进行 concat() 操作的参数是数组，那么添加的是数组中的元素，而不是数组。</p>
</div>
<h2 id="spliceUsing">splice()函数</h2>
<div>
<p>splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目。<strong>注意：该方法会改变原始数组</strong></p>
<h3>语法</h3>
<pre><code>
arrayObject.splice(index,howmany,item1,.....,itemX);
</code></pre>
<p>
其中index是必需项，整数，规定添加/删除项目的位置，如果是负数，则会加上数组的长度作为start的值；howmany必需，表示要删除的项目数量，如果设置为 0或者负数，则不会删除项目；<strong>item1,...itemX可选项，表示向数组对象中添加新的项目。</strong>
</p>
</div>
<h2 id="mapUsing">map()函数</h2>
<div>
<p>对数组的每个元素调用定义的回调函数并返回包含结果的数组，该返回数组是一个新的数组，其中的每个元素均为关联的原始数组元素的回调函数返回值。</p>
<h3>语法</h3>
<pre><code>
array1.map(callbackfn[, thisArg]);
//回调函数语法
function callbackfn(value, index, array1)
</code></pre>
<table>
<tr><th>回调参数</th><th>定义</th></tr>
<tr><td>value</td><td>数组元素的值</td></tr>
<tr><td>index</td><td>数组元素的数字索引</td></tr>
<tr><td>array1</td><td>包含该元素的数组对象</td></tr>
</table>
</div>
<h2 id="applyUsing">call()、apply()和bind()函数</h2>
<div>
<p>call()和apply()用法一样，区别在于参数的形式不同，前者是详细参数，后者是一个数组，数组的元素对应前者的详细参数。</p>
<h3>apply()</h3>
<pre><code>
Function.apply(obj,arr);
</code></pre>
<p>obj是一个对象，它将代替Function的this对象。通俗讲，obj将会调用Function函数，且调用的参数为arr数组的每个元素。假如arr=[par1,par2,par3,par4]，Function执行的时候就是Function(ar1,par2,par3,par4)。由于apply()的特性，可以有一些巧妙的用法：</p>
<p><strong>1.取数组的最值问题：</strong>
<pre><code>
var max = Math.max.apply(null,arr);
</code></pre>
</p>
<p>由于Math.max(par1,par2,par3,...)是成立的，而不存在Math.max([par1,par2,par3,...])，因此使用apply方法可以很方便地求取数组元素中的最值问题（min等同于max）。<strong>注：这里apply的第一个参数取的null，是因为不需要有对象调用Math.max（）方法，只需要执行该方法即可。</strong></p>
<p><strong>2.数组合并问题：</strong>
<pre><code>
Array.prototype.push.apply(arr1,arr2);
</code></pre>
</p>
<p>由于push方法也是对详细参数的一个操作，将数组作为push的参数添加的是一个数组而非每个元素，所以apply方法能够简化数组的合并操作。<strong>注：push(pop)方法是在原数组最后添加(删除)元素，对原数组进行了修改（数组长度、内容都变化了）。</strong></p>
<h3>bind()</h3>
<p>bind()是ECMAScript 5.1新增的扩展方法（IE8/7/6不支持），bind与call很相似，例如，可接受的参数都分为两部分，且第一个参数都是作为执行时函数上下文中的this的对象。不同点有二：</p>
<p>1.bind（）返回值是改变上下文this后的函数，而call（）是改变上下文this并执行函数</p>
<pre><code>
var a = func.bind(obj,para1,para2,...);//a的值是func(),它由obj调用，且参数为para1,para2,...
var b = func.call(obj,para1,para2,...);//b的值是obj执行函数func(para1,para2,...)的结果
</code></pre>
<p>2.后面的参数在使用上的区别</p>
<pre><code>
function fun(a,b,c){
    console.log(a,b,c);
}
var funEx = fun.bind(null,'A_Ex');
fun('A','B','C');//输出 A B C
fun.call(null,'A');//输出  A undefined undefined
funEx('B','C');//输出  A_Ex B C
funEx('B');//输出  A_Ex B undefined
funEx('A','B','C');//输出  A_Ex A B
</code></pre>
<p>
由此可以看出，call是把第二个及以后的参数作为fun方法的实参传进去，而bind虽说也是获取第二个及以后的参数用于之后方法的执行，但是fun_Ex中传入的实参则是在bind中传入参数的基础上往后排的。
</p>
</div>

