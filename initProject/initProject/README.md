# node.js
nodejs笔记


模块演变——全局函数
1.html：
实现一个简易计算器
缺点：全局变量污染、生存期长


模块演变——函数封装
2.html：
实现简易计算器
把所有函数封装到一个对象中，这个对象可以从程序级别分出功能模块，降低了命名冲突的概率，但是并没有从根本上解决问题。
另一种说法：命名空间

模块演变——隔离公有私有成员
3.html：匿名函数自执行  隔离公有私有成员，进一步降低命名冲突的概率

模块演变——增强代码可维护性
4.html：开闭原则：对修改封闭，对添加开放；原理：通过参数形式划分子模块，进一步增强模块可维护性和可扩展性

------------------------------------------------------------------------------------------------------------------------------------------


node全局对象：global  process  console  Buffer

nodejs模块化：
（1）module.exports和exports指向是一样的，都是一个空对象（object的实例对象），实际导出的成员以module.exports为准
（2）一般模块导出单个成员的时候使用exports
（3）一般模块导出构造函数的实例对象时使用module.exports
（4）通过global也可以公开成员，使用global时不需要返回值，只require进来就可以，即使有返回值也取不到global
（5）模块require引入的时候，如果多次引入同一个模块，那么也不会加载多次，因为在第一次引入的时候模块已经缓存了

可以作为文件的格式：
（1）无后缀
（2）.js
（3）.json
（4）.node
文件执行优先级：无后缀 -> .js -> .json -> .node -> 文件夹

---------------------------------------------------------------------------------------------------------------------------------------

package.josn属性注意事项:
name:(1)长度必须小于214个字符
     (2)不能以 . 和_ 开头
     (3)不能含有大写字母
     (4)不能含有非URL安全的字符（eg：/ ： &）
