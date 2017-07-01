# 遍历对象的key

当要取得一个对象自身全部的键名时，使用较多的方法就是`Object.keys()`。

但是当对象的键名是以`Symbol`值来定义的时候，`Object.keys()`就无法得到期望中的包含`Symbol`键名的数组了。

这时可以使用`Object.getOwnPropertySymbols()`来取得以`Symbol`值作为键名的的数组，然后再配合`Object.getOwnPropertyNames().concat(Object.getOwnPropertySymbols())`就可以得到包含常规字符串和`Symbol`键名的数组了。

不过上面这段操作实在是太长了，有个更加省力的方法就是使用`Reflect.ownKeys()`。`Reflect`对象的`ownKeys`方法返回一个对象自身的键名数组，它能处理的键名类型比上面的方法多。
