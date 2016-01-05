#setter & getter
```javascript
let setget = {
	get foo(){
		console.log("foo fun");
		return "foo fun return";
	},
	set bar(value){
		console.log(`set bar to ${value}`);
	}
}

> setget.foo;
//GET foo
//123

> setget.bar = "yangfei"
//set bar to yang
```