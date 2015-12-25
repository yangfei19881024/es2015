#generator next传值
```
function* dataConsumer() {
    console.log('Started');
    console.log(`1. ${yield}`); // (A)
    console.log(`2. ${yield}`);
    return 'result';
}
首先，创建一个生成器对象：

> let genObj = dataConsumer();

> genObj.next()
Started
{ value: undefined, done: false }

> genObj.next('a')
1. a
{ value: undefined, done: false }

> genObj.next('b')
2. b
{ value: 'result', done: true }
```
##很不幸， next() 是非对称的：它总是传值给当前暂停的 yield ，返回下一个 yield 的操作数。
#第一个 next()
```
在把生成器当成观察者的时候，一定要注意第一次 next() 调用是为了启动观察者，然后才接收输入，因为第一次调用使执行流程推进到了第一个 yield 处。因此，不能通过第一个 next() 传送值 - 如果这样做了，甚至会得到一个错误：

> function* g() { yield }
> g().next('hello')
TypeError: attempt to send 'hello' to newborn generator
```

