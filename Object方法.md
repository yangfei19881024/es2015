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