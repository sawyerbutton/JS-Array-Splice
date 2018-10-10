# JS-Array-Splice

## 使用Splice方法处理Array的基本技巧

> `splice()`方法允许从javascript数组中插入，删除和替换元素

> `splice()`方法接受三+个参数 `Array.splice(start_index, number_of_elements_to_remove)`

1. `start_index` 指的是在数组中插入或移除元素的位置
2. `number_of_elements_to_remove` 将从`start_index'索引开始，并从数组中删除一个元素
3. `number_of_elements_to_remove`之后的所有参数都将从`start_index`的位置插入到数组中，插入到数组中的参数可以是任何数据类型，包括字符串，数字，布尔值，对象，函数，null，undefined

### 示例-如何将数字插入数组中

```javascript
var my_array = [1,3,4];
var start_index = 1;
var number_of_elements_to_remove = 0; // 需要删除的元素个数为0
my_array.splice(start_index, number_of_elements_to_remove, 2);
console.log(my_array);
//[1,2,3,4];
```

> 值得注意的是,使用`array.splice()`方法时,方法将直接作用于数组

> 因此调用`my_array`上的`splice()`方法将不会返回一个新数组而是更新`my_array`

### 示例-如何从数组中移除一个元素

```javascript
var my_array = ["a","b","c","k","d"];
var start_index = 3
var number_of_elements_to_remove = 1;
var removed_elements = my_array.splice(start_index, number_of_elements_to_remove); // splice方法返回被删除的元素
console.log(removed_elements);
//["k"]
console.log(my_array);
//["a","b","c","d"];
```

> 值得注意的是,使用`splice`方法删除的元素将会作为一个包含删除元素的数组返回

### 示例-如何替换数组中一些元素

```javascript
var my_array = ["baseball", "basketball", "tennis", "golf"];
var start_index = 1
var number_of_elements_to_remove = 2;
var removed_elements = my_array.splice(start_index, number_of_elements_to_remove, "boxing", "bowling", "volleyball"); // 移除两个元素后添加三个元素
console.log(removed_elements);
//["tennis", "golf"]
console.log(my_array);
//["baseball", "boxing", "bowling", "volleyball", "golf"];
```

> 上述`splice()`方法的调用看起来很长,拆分为步骤来看

1. `splice()`方法从`my_array[1]`开始
2. 移除`my_array`的`index`为1和2的元素
3. 最后，从`my_array`的1位置将新参数逐个添加进array中

### 总结

> 当希望向javascript数组中增加或移除元素时`splice()`方法得心应手

> 如果数组已排序，则`splice()`方法可以很好地添加新元素并精确定位到数组中所需的位置。

> 同样在通过索引从数组中删除元素时`splice()`方法也很得心应手

> 需要注意的是`splice()`方法直接作用于源数组

> 只有通过`splice()`方法删除的元素才会被方法正确返回,添加元素返回的值将为空数组