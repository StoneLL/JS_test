# JS数据类型
> 数据类型分未两类： 1.**原始类型** 2.**对象类型**

## **原始类型：**
- 1. 数字、字符串、布尔值
    ```js 不区分整数和浮点数，统一用number表示。```

- 2. 特殊的原始值：**null（空）** 、**undefined（未定义）**

## **对象类型**
> 对象（object）是属性（property）的集合，每个属性都由“名/值对”组成（值对可以是原始类型，也可以是对象）
 ### **特殊对象**：
 - 1. 数组：表示带编号的值的有序集合，有专用的语法。
 - 2. 函数：具有与它有关联的可执行的代码的对象，通过调用函数来运行可执行的代码，并返回运算结果。

 ## 对象(变量)
    javascript的对象是一组```健-值```组成的无序集合。其中每个健称之为对象的属性，获取对象的属性就可以得到对应属性的值。

- javascript的所有属性都是字符串，属性对应的值可以是任意数据类型。
- 访问一个不存在的属性会返回undefined（未定义）。
- javascript的对象是动态类型，可以自有的给一个对象添加或删除属性。

### 判断一个对象是否存在某一属性

- 使用in操作符判断是否存在某一属性
```
    var xiaoming = {
    name: '小明',
    birth: 1990,
    school: 'No.1 Middle School',
    height: 1.70,
    weight: 65,
    score: null
};
'name' in xiaoming;     // true
'grade' in xiaoming;     // false
```
     此方法不能判断继承所得的属性 

- hasOwnProperty()方法判断
```
    var xiaoming = {
    name: '小明'
    };
    xiaoming.hasOwnProperty('name');     // true
    xiaoming.hasOwnProperty('toString');     // false
```
    
---
## 字符串
### 转义字符
    可以使用“\”实现;还可以使用`\n`表示换行,`\t`标识制表符等。

### 多行字符串
    使用 反引号`....`表示。

## 数组
- 数组可以通过索引修改对应的数组内的值。
### 可以通过indexOf()来搜索指定元素的位置
``` 
    var arr = [10,20,'30','xyz'];
    arr.indexOf(10);    //元素的索引为0
    arr.indexOf('30');  //元素的索引为2
    arr.indexOf(30);    //数组中没有这个元素，返回-1
```
> ```数字30和字符串`30`是不同元素```

### sort()可以对数组内元素进行排序
```
    var arr = ['b','c','a'];
    arr.sort();
    arr;    //返回结果为：['a','b','c']
```
### reverse()将整个数组（Array）内的元素反转
```
    var arr = ['one','two','three'];
    arr.reverse();
    arr;    //返回结果为： ['three','two','one']
```
### splice()方法可以从指定索引开始删除若干元素，然后从该位置添加若干元素
```
    var arr = ['Microsoft', 'Apple', 'Yahoo', 'AOL', 'Excite', 'Oracle'];
    // 从索引2开始删除3个元素,然后再添加两个元素:
    arr.splice(2, 3, 'Google', 'Facebook'); // 返回删除的元素 ['Yahoo', 'AOL', 'Excite']
    arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
    // 只删除,不添加:
    arr.splice(2, 2); // ['Google', 'Facebook']
    arr; // ['Microsoft', 'Apple', 'Oracle']
    // 只添加,不删除:
    arr.splice(2, 0, 'Google', 'Facebook'); // 返回[],因为没有删除任何元素
    arr; // ['Microsoft', 'Apple', 'Google', 'Facebook', 'Oracle']
```

### concat()可以把当前数组和另外一个数组连接起来，并返回一个新的数组
```
    var arr = ['A', 'B', 'C'];
    var added = arr.concat([1, 2, 3]);
    added; // 返回结果：['A', 'B', 'C', 1, 2, 3]
    arr; // 连接不会影响原有的数组：['A', 'B', 'C']
```
### join()方法可以把当前数组内的元素使用指定的字符串连起来，然后返回连接后的字符串。
- 如果数组内的元素不是字符串，将自动转换为字符串后连接起来。
```
    var arr = ['A', 'B', 'C', 1, 2, 3];
    arr.join('-'); // 返回结果：'A-B-C-1-2-3'
```
---
## 条件判断

    可使用if(){...}else{...}来进行条件判断.

```
    var age = 20;
    if (age >= 18) {     // 如果age >= 18为true，则执行if语句块
        alert('adult');
    } else {    // 否则执行else语句块
        alert('teenager');
    }
```

### 多条件判断
- 如果要更加细致的判断条件，可用多级if... else... 的组合.

```
    var age = 3;
    if (age >= 18) {
        alert('adult');
    } else {
        if (age >= 6) {
            alert('teenager');
        } else {
            alert('kid');
        }
    }
```
---

## 循环


### javascript循环之for循环
- 通过初始条件、结束条件和递增条件来循环执行语句块。

```
    var x = 0;
    var i;
    for (i=1; i<=10000; i++) {
        x = x + i;
    }
    x;
    //其中：（i=1）为初始条件；（i<=10000）为结束条件；（i++）为递增条件
```
- for循环常用来利用索引遍历数组
```
    var arr = ['Apple', 'Google', 'Microsoft'];
    var i, x;
    for (i=0; i<arr.length; i++) {
        x = arr[i]; 
        alert(x);
    }   //结果会逐个打印数组内的元素
```

