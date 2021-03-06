# 9 differences between Array and ArrayList in Java

**Java 中数组和 ArrayList 的 9 个区别**

> 转译自：https://www.javacodegeeks.com/2016/01/9-differences-between-array-and-arraylist-in-java.html

Both array and ArrayList are two important data structures in Java and are frequentl used in Java programs. Even though ArrayList is internally backed by an array, knowing the difference between an array and an ArrayList in Java is critical for becoming a good Java developer. If you know the similarity and differences, you can judiciously decide when to use an array over an AraryList or vice-versa.

数组和 ArrayList 都是 Java 中非常重要的数据结构，在 Java 程序中经常使用。虽然 ArrayList 是由数组内部支持的，了解 Java 中数组和 ArrayList 之间的区别对于成为一名优秀的 Java 开发人员至关重要。如果你知道相似性和差异性，你就可以明智地决定何时以 AraryList（取代）数组，反之亦然。

In this article, I’ll help you understand the difference. If you are coming from C or C++ background then you already know that array is one of the most useful data structure in the programming world. It offers O(1) performance for index-based search and one of the fundamental way to store data.

在本文中，我将帮助你理解其中的区别。如果你有 C 或 C++ 背景，那么肯定知道数组是编程世界中最有用的数据结构之一。它为基于索引的搜索提供了 O(1) 性能，是存储数据的基本方式之一。

The ArrayList one the other hand is a class in Java Collection framework which was introduced as a dynamic array. Since an array is static in nature i.e. you cannot change the size of an array once created, So, if you need an array which can resize itself then you should use the ArrayList. This is the fundamental difference between an array and an ArrayList.

ArrayList 是 Java 集合框架中的一个类，作为动态数组引入。由于数组本质上是静态的，也就是说，一旦创建了数组，你就不能更改数组的大小，因此，如果你需要一个能够调整自身大小的数组，那么你应该使用 ArrayList。这是数组和 ArrayList 的基本区别。

## Array vs ArrayList in Java

**Java 中的数组与 ArrayList**

It’s best to compare two things on some points, this will make the differences easy to understand. So let’s see what are the points on which you can compare an array with the ArrayList in Java

最好在某些技术点上比较两件事情，这将使两者的区别容易理解。那么，让我们看看在哪些技术点上可以将数组与 Java 中的 ArrayList 进行比较。

## 1、Implementation

**实现**

The array is a native programming component or data structure but ArrayList is a class from Java Collections framework, an API. In fact, ArrayList is internally implemented using an array. Since ArrayList is a class, it holds all properties of a class e.g. you can create objects and call methods but even though the array is an object in Java it doesn’t provide any method. It just exposes a length attribute to give you the length of the array, which is constant.

数组是原生编程组件或数据结构，而 ArrayList 是 Java 集合框架中的一个类，是一个 API。实际上，ArrayList 内部是使用数组实现的。因为 ArrayList 是一个类，它包含一个类的所有属性，例如，你可以创建对象和调用方法，但即使数组是 Java 中的一个对象，它也不提供任何方法。它只是公开了一个 length 属性来给你数组的长度，这是常量。

## 2、Performance

**性能**

Since ArrayList is based upon array, you would assume that it provides the same performance as an array. This is true at some extent but because of extra functionality ArrayList provides there is some difference in performance between ArrayList and array, mainly in terms of memory usage and CPU time.

由于 ArrayList 是基于数组的，因此可以假设它提供了与数组相同的性能。这在某种程度上是正确的，但是由于 ArrayList 提供了额外的功能，所以 ArrayList 和数组之间的性能有一些不同，主要是在内存使用和 CPU 时间方面。

For index-based access, both ArrayList and array provides **O(1)** performance but add can be **O(logN)** in ArrayList if adding a new element triggers resize, as it involves creating a new array in background and copying elements from the old array to new array. The memory requirement for ArrayList is also more than an array for storing the same number of objects e.g. an int[] will take less memory to store 20 int variables than an ArrayList because of object metadata overhead on both ArrayList and wrapper class.

对于基于索引的访问，ArrayList 和数组都提供了 O(1) 性能，但是如果在 ArrayList 中添加一个新元素会触发调整大小，那么 add 可以是 O(logN)，因为它涉及在后台创建一个新数组，并将元素从旧数组复制到新数组。ArrayList 的内存需求也不仅仅是存储相同数量对象的数组，例如 int[] 比 ArrayList 存储 20 个 int 变量所需内存更少，因为 ArrayList 和包装类上都有对象元数据开销。

## 3、Type Safety

**类型安全**

ArrayList is type safe because it supports generics which allows the compiler to check if all objects stored in ArrayList are of the correct type. On the other hand, the array doesn’t support Generics. Which means compile time checking is not possible but array provides runtime type checking by throwing ArrayStoreException if you try to store an incorrect object into array e.g. storing a String into an int array.

ArrayList 是类型安全的，因为它支持泛型，允许编译器检查存储在 ArrayList 中的所有对象是否都是正确的类型。另一方面，数组不支持泛型。这意味着编译时检查是不可能的，但是如果你试图将一个不正确的对象存储到数组中，例如将一个字符串存储到 int 数组中，数组通过抛出 ArrayStoreException（体现）提供了运行时类型检查。

## 4、Flexibility

**灵活性**

Flexibility is the single most important thing that separates array and ArrayList. In short, ArrayList is more flexible than a plain native array because it’s dynamic. It can grow itself when needed, which is not possible with the native array. ArrayList also allows you to remove elements which are not possible with native arrays. By remove, we mean not just assigning null to the corresponding index but also copying rest of elements one index down, which ArrayList automatically does for you. You can learn more about removing objects from ArayList in my article **_difference between clear() and removeAll()_**.

灵活性是区分数组和数组列表最重要的一点。简而言之，ArrayList 比普通的原生数组更灵活，因为它是动态的。它可以在需要时自行增长，这在原生数组中是不可能的。ArrayList 还允许删除原生数组无法删除的元素。所谓删除，我们的意思不仅仅是给相应的索引分配 null，还包括将其他元素的一个索引复制下来，ArrayList 会自动为你这样做。在我的文章《clear() 和 removeAll() 的区别》中，你可以了解关于从 ArayList 中删除对象的更多信息。

## 5、Primitives

**基本数据类型**

If you first start using ArrayList then you will realize that you cannot store primitives on ArrayList. This is a key difference between array and ArrayList because array allows storing both primitives and object. For example int[] numbers are valid but ArrayList of int is not valid. how do you deal with this problem?

如果你第一次开始使用 ArrayList，那么你将意识到不能在 ArrayList 上存储基本数据类型。这是数组和 ArrayList 之间的一个关键区别，因为数组允许存储基本数据类型和对象。例如 int[] 数字是有效的，但是 ArrayList 是无效的。你如何处理这个问题？

Suppose you want to store int primitives into ArrayList than how do you that? Well, you can use the wrapper class. This is one of the reasons why wrapper class was introduced in Java. So if you want to store int 2 into ArrayList just put it, autoboxing will do the rest. Btw, this difference is not so obvious from Java 5 onwards because of auto-boxing as you will see that ArrayList.add(21) is perfectly valid and works.

假设你想把 int 类型存储到 ArrayList 中，你会怎么做？你可以使用包装器类。这是 Java 中引入包装类的原因之一。如果你想把 int 2 存储到 ArrayList 中，只要把它放进去，自动装箱就能完成剩下的。顺便说一下，从 Java 5 开始，由于自动装箱的原因，这种差异就不那么明显了，因为你将看到 ArrayList.add(21) 是完全有效的，并且可以工作。

## 6、Generics

**泛型**

One more significant（重要的） difference between an ArrayList and an array is that the former supports Generic but the latter doesn’t. Since an array is of covariant type, you can use Generics with them. This means it’s not possible for a compiler to check the type-safety of an array at compile time but they can verify type-safety of Array. So how do you deal with this problem while writing a type-safe class in Java? Well, you can use the technique shown in Effective Java, where you can declare an array like E[] and later use type casting.

ArrayList 和数组的另一个重要区别是前者支持泛型，而后者不支持泛型。由于数组是协变类型的，所以可以使用泛型。这意味着编译器不可能在编译时检查数组的类型安全性，但它们可以验证数组的类型安全性。那么，在用 Java 编写类型安全类时，如何处理这个问题呢？你可以使用 Effective Java 中所示的技术，可以声明一个像 E[] 这样的数组，然后使用类型转换。

## 7、Iteration

**迭代**

ArrayList provides more ways for iteration i.e. accessing all elements one by one than an array. You can only use loop e.g. for, while, enhanced for loop and do-while to iterate over an array but you can also use Iterator and ListIterator class to iterate over ArrayList. See here to learn different ways to iterate over ArrayList in Java.

ArrayList 相比数组而言为迭代，即逐个访问所有元素，提供了更多的方法。你只能使用 for 循环、 while 循环、增强 for 循环和 do-while 来迭代数组，但你也可以使用 Iterator 和 ListIterator 类来迭代 ArrayList。请参阅此处以了解在 Java 中迭代 ArrayList 的不同方法。

## 8、Supported Operations

**运算符支持**

Since ArrayList is backed by an array internally, it exposes（揭露） the operation which is possible with an array but given its dynamic nature it also added operation which is not possible with native array e.g. you can store elements in both array and ArrayList, but only ArrayList allows you to remove an element. Though you can simulate that with an array by assigning null to respective index, it won’t be like remove unless you also move all element above that index in the array to one level down.

因为 ArrayList 是由数组在内部支持的，所以它公开了使用数组可以实现的操作，但考虑到它的动态特性，它还添加了使用原生数组不可能实现的操作，例如，你可以在数组和 ArrayList 中存储元素，但只有 ArrayList 允许你删除元素。虽然你可以通过将 null 赋值给相应的索引来模拟这个过程，但是它不会像 remove （方法）那样，除非你还将数组中位于该索引之上的所有元素向下移动一层。

Both ArrayList and array provide ways to retrieve an element e.g. get() method of ArrayList uses an index to get an element from array e.g. version[0] will return the first element.

ArrayList 和数组都提供了检索元素的方法，例如 ArrayList 的 get() 方法使用索引从数组中获取元素，例如 version[0] 将返回第一个元素。

ArrayList also provides an operation to clear and reuse（重 chong 用） e.g. clear() and removeAll(), the array doesn’t provide that but you can loop over Array and assign each index null to simulate that.

ArrayList 还提供了一个清除和重用的操作，例如 clear() 和 removeAll()，数组没有提供这个功能，但是你可以用循环数组，为每个索引分配 null 的方式来模拟它。

## 9、Size() vs length

**Size() 方法与 length 属性**

Array only provides a length attribute which tells you the number of slots in the array i.e. how many elements it can store, it doesn’t provide you any method to find out how many are filled and how many slots are empty i.e. the current number of elements. While ArrayList does provides a size() method which tells a number of objects stored in ArrayList at a given point of time. The size() is always different than length, which is also the capacity of ArrayList. If you want to know more, I suggest you read the difference between size() and length in ArrayList article.

数组只提供一个 length 属性，它告诉你数组中的槽数，也就是它可以存储多少个元素，它不提供任何方法来找出有多少个被填充，有多少个槽是空的，也就是当前元素的数量。虽然 ArrayList 提供了一个 size() 方法，它告诉在给定时间点存储在 ArrayList 中的许多对象。size() 总是与 length 不同，length 也是 ArrayList 的容量。如果你想了解更多，我建议你阅读 ArrayList 文章中的 size() 和 length 之间的区别。

## 10、Dimension

**维度**

Another significant（重要的） difference between an array and an ArrayList is that array can be multi-dimensional e.g. you can have a two-dimensional array or a three-dimensional array, which makes it a really special data structure to represent matrices and 2D terrains. On the other hand, ArrayList doesn’t allow you to specify dimension. See this tutorial learn more about how to use a multi-dimensional array in Java.

数组和 ArrayList 的另一个重要区别是，数组可以是多维的，例如，你可以有一个二维数组或三维数组，这使得它可以成为一种非常特殊的数据结构来表示矩阵和二维地形。另一方面，ArrayList 不允许指定维度。请参阅本教程，了解如何在 Java 中使用多维数组。

Here is the nice slide highlighting all important difference between Array and ArrayList in Java:

下面这张幻灯片（**注：已将图片内容转为文字**）突出了 Java 中数组和 ArrayList 的所有重要区别：

## Difference between array vs ArrayList in Java

**Java 中数组与 ArrayList 的区别**

1、An array is static, you cannot change it's length once created, but ArrayList is dynamic, it can grow to accommodate more elements.

数组是静态的，一旦创建就不能改变它的长度，但是 ArrayList 是动态的，它可以增长以适应更多的元素。

2、The array doesn't support generics, hence they are not type-safe but ArrayList support Generics, hence they provide compile time type-safety.

数组不支持泛型，因此它们不是类型安全的，但是 ArrayList 支持泛型，因此它们提供编译时类型安全。

3、Array takes less memory than Arrayist for storing same number of elements or objects.

在存储相同数量的元素或对象时，数组比 Arrayist 占用更少的内存。

4、ArrayList allows you to remove element, but array doesn't provide such methods.

ArrayList 允许删除元素，但数组不提供这样的方法。

5、Array can accommodate both primitive and objects, but Arraylist can only accommodate objects.

数组可以同时容纳基础数据类型和对象，但 Arraylist 只能容纳对象。

译注：本文第 5 点提到了，从 Java 5 开始 Arraylist 也能容纳基础数据类型

6、Array can be multi-dimensional but ArrayList is always one dimensional.

数组可以是多维的，但 ArrayList 总是一维的。

译注：应该说 ArrayList 默认是一维的，如果每个元素也是一个 ArrayList，可以间接实现多维

7、Array provides length attribute and ArrayList provides size() but both are different, length is capacity, while size() return number of elements.

数组提供 length 属性，ArrayList 提供 size()，但两者不同，length 是容量，size() 返回元素数量。

## Similarities between Array and ArrayList

**数组和数组列表的相似性**

So far you have seen the difference between an ArrayList and an array, now let’s concentrate（关注） on some of the similarities. Since ArrayList internally uses array, it’s bound to have lot of similarities as seen below:

到目前为止，你已经看到了 ArrayList 和数组之间的区别，现在让我们关注一些相似之处。由于 ArrayList 内部使用数组，两者肯定有很多相似之处，如下所示：

## 1、Data Structure

**数据结构**

Both allow you to store objects in Java and both are an index-based data structure which provides O(1) performance to retrieve an element, but search without an index is still log(N) if your array is sorted and you use binary search algorithm.

这两种方法都允许在 Java 中存储对象，并且都是基于索引的数据结构，它提供了 O(1) 性能来检索元素，但是如果数组是有序的，并且使用二进制搜索算法，那么没有索引的搜索仍然是 log(N)。

## 2、Order

**有序性**

Both array and ArrayList maintain order on which elements are added into them.

数组和 ArrayList 的元素顺序就是添加时的顺序。

## 3、Search

**搜索**

You can search for an element using an index, that’s O(1) otherwise you can use linear search if your array is not sorted, which takes around O(n) time or you can use binary search after sorting an array in Java, this is sorting + O(logN).

你可以用索引来搜索一个元素，它是 O(1) 的，如果你的数组没有排序，你可以用线性搜索，这需要大约 O(n) 的时间，或者你可以用二分法检索，在 Java 中对一个数组排序后，这种排序的时间复杂度为 O(logN)。

## 4、Null values

**Null 值**

Both array and ArrayList allow null values but remember only object array allows null primitive array doesn’t they store the default value of primitive type e.g. zero for int and false for boolean.

数组和 ArrayList 都允许 null 值，但记住只有对象数组允许 null 基本数据类型数组，它们不存储基本数据类型类型的默认值，例如，0 表示 int, false 表示 boolean。

## 5、Duplicates

**重复**

Both array and ArrayList allow duplicates. It’s also one of the common array based coding questions to write a program to find out duplicates from an array in place.

数组和 ArrayList 都允许（元素）重复。它也是一个常见的基于数组的编码问题，即编写一个程序从一个数组中找出（元素）副本。

## 6、Performance

**性能**

ArrayList mimic array’s performance e.g. O(1) access if you know the index but it has additional memory overhead because it’s an object and also holds additional data to automatic resize the ArrayList.

ArrayList 模拟数组的性能，如 O(1) 访问，如果你知道索引，但是它有额外的内存开销，因为它是一个对象，而且还包含额外的数据来自动调整 ArrayList 的大小。

## 7、Zero-based Index

**从零开始的索引**

Both array and ArrayList have zero-based index i.e. first element starts at zeroth index.

数组和 ArrayList 都有从零开始的索引，即第一个元素从第 0 个索引开始。

The most important difference you should remember is that array is static in nature i.e. you cannot change their size once created but ArrayList is a dynamic array, which can resize itself if a number of elements in the ArrayList are more than the resize threshold. Based upon this difference, you should use an array as a data structure to store objects if you know the size in advance and sure it’s not going to change, if you are unsure then just use the ArrayList.

你应该记住的最重要的区别是数组本质上是静态的，也就是说你不能改变它们的大小，但是 ArrayList 是一个动态数组，如果 ArrayList 中的一些元素超过了阈值，它可以调整自己的大小。基于这种差异，如果你事先知道对象的大小并且确定不会改变对象的大小，那么你应该使用数组作为数据结构来存储对象，如果你不确定，那么就使用 ArrayList。
