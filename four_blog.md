##	Lodash——Javascript库之Array篇
这几天又学到了不少原来不知道的知识，在周末中总结了些Javascript库—lodash（Array）篇的内容，希望在以后的学习中不时的自己去复习和更新。

 lodash—JavaScript工具库，现今非常流行，下面是我对它的一些代码的总结：

1._.chunk  指按照指定的长度去合并数组的元素。

_.chunk(['a', 'b', 'c', 'd'], 2);  

// → [['a', 'b'], ['c', 'd']]  

_.chunk(['a', 'b', 'c', 'd'], 3);  

// → [['a', 'b', 'c'], ['d']]  

2._.compact  删除数组元素中的虚假值。

_.compact([0, 1, false, 2, '', 3]);  

// → [1, 2, 3]  

3._.drop 可以输出删除指定位置的元素（默认值为1），若为0，则返回原数组。

_.drop([1, 2, 3]);  

// → [2, 3]  

_.drop([1, 2, 3], 2);  

// → [3]  

 _.drop([1, 2, 3], 5);  

// → []

_.drop([1, 2, 3], 0);  

// → [1, 2, 3]                   //这个就是返回了原数组。

4. _.difference 在第一个数组元素中删除与第二个数组相同的元素。

_.difference([1, 2, 3], [5, 2, 10]);  

// → [1, 3]

5._.intersetion  通过找到几个数组中共有的元素，然后进行输出。

_.intersection([1, 2, 3], [5, 2, 1, 4], [2, 1]);  

// → [1, 2]  

6._.dropRight  我自己认为这个和_.drop基本用法相同，只不过这个是从右侧进行删除。

7._.findIndex  可以输出相反的满足条件对象的个数。

var users = [  { 'user': 'barney',  'age': 36, 'active': false },  { 'user': 'fred',    'age': 40, 'active': true },                                                      { 'user': 'pebbles', 'age': 1,  'active': false }  ];  

_.findIndex(users, function(chr) { return chr.age < 40; });  

// → 0  

_.findIndex(users, { 'age': 1 });  

// → 2

8. (1.)_.first 输出第一个元素.

_.first([1, 2, 3]);  

// → 1  

_.first([]);  

// → undefined  

(2.)_.rest 输出除第一个元素的剩下元素。

_.rest([1, 2, 3]);  

// → [2, 3]

(3)_.last 输出最后一个元素

 _.last([1, 2, 3]);  

// → 3  

(4.)_.initial 输出除最后一个元素的剩下元素

 _.initial([1, 2, 3]);  

// → [1, 2]  

9. 原数组删除2, 3后输出.

var array = [1, 2, 3, 1, 2, 3];  

_.pull(array, 2, 3);  

console.log(array);  

// → [1, 1]

10._.without去掉数组中的元素。

.without([1, 2, 1, 0, 3, 1, 4], 0, 1);  

// → [2, 3, 4]  
