#Object 新增方法
#给 this 添加属性
```
class Point {
    constructor(name, age) {
        Object.assign(this, {name, age});
    }
		get p(){
			console.log(this);
		}
}

var pp = new Point("tomcat",12);
console.log(pp.name);
**上面代码相当于**
class Point {
    constructor(name, age) {
        this.name = name;
        this.age = age;
    }
		get p(){
			console.log(this);
		}
}

```

##给对象属性提供默认值
```javascript
const DEFAULTS = {
    logLevel: 0,
    outputFormat: 'html'
};
function processContent(options) {
    options = Object.assign({}, DEFAULTS, options); // (A)
		console.log(options);
}

processContent({
	name: "yang",
	age:28
})

//Object {logLevel: 0, outputFormat: "html", name: "yang", age: 28}
```

##给对象添加方法
```javascript
Object.assign(SomeClass.prototype, {
    someMethod(arg1, arg2) {
        ···
    },
    anotherMethod() {
        ···
    }
});
//相当于
SomeClass.prototype.someMethod = function (arg1, arg2) {
    ···
};
SomeClass.prototype.anotherMethod = function () {
    ···
};
```