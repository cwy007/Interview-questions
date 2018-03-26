# Interview-questions（每日一题）

#### 那些操作会造成内存泄漏?
- 内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。垃圾回收器定期扫描对象,并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为0(没有其他对象引引用过该对象),或对该对象的惟一引用是循环的,那么该对象的内存即可回收。

- settimeout的第一个参数使用字符串而非函数的话,会引发内存泄漏。
闭包、控制台日志、循环(在两个对象彼此引用且彼此保留时,就会产生一个循环)





#### Js垃圾回收方法？

- 标记清除（mark and sweep）
  这是js最常见的垃圾回收方式，当变量进入执行环境的时候，比如函数中声明一个变量，垃圾回收器将其标记为“进入环境”，当变量离开环境的时候（函数执行结束）将其标记为“离开环境”。
  垃圾回收器会在运行的时候给存储在内存中的所有变量加上标记，然后去掉环境中的变量以及被环境中变量所引用的变量（闭包），在这些完成之后仍然存在标记的就是要删除的变量。
  
 - 引用计数（reference counting）
   在低版本IE中经常出现内存泄漏，很多时候就是因为采用引用技术的方式进行垃圾回收。
   引用计数的策略是跟踪记录每个值被引用的次数，当声明一个变量并将一个引用类型赋值给该变量的时候这个值的引用次数+1，如果该变量的值变成了另一个，则这个值的引用次数-1，当引用次数为0的时候就回收。
   
   
#### 堆栈的区别？
