# Big O Notation

Big O Notation is used to describe the performance on **algorithm**.
That way its easy for us to determine if the given algorithm is **scaleable** or not.
Thats mean we can point if the algorithm will scale well as the **input grows**.


```
Big O Notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity.
- Wikipedia
```

Certain operations can be more or less costly depending on what **data structure** we use.

Let's take a look an **array** for example:

It will be super fast to access an array element by its index. However, **arrays** have **fixed length**. So if we want to add or remove elements from them, they have to get **resized**. This will not **scale** well as the **size** of an array grows **very large**.

So for this particular problem, it's better to use another data structure called **Linked List**.
**Linked List** data structure can grow or shrink very quickly, but accessing a linke list element by its index is slow.

Let's try to describe the performance of an algorithm. That way we will get better understanding of **Big O Notation**.

The first example in our Java Program will take an array of integers and prints