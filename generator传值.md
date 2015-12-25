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

> genObj.next('a')
1. a
{ value: undefined, done: false }

> genObj.next('b')
2. b
{ value: 'result', done: true }
```
*很不幸， next() 是非对称的：它总是传值给当前暂停的 yield ，返回下一个 yield 的操作数。*

