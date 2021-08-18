# Big O Notation

Big O Notation is used to describe the performance on **algorithm**.
That way it's easy for us to determine if the given algorithm is **scaleable** or not.
That means we can point if the algorithm will scale well as the **input grows**.


```
Big O Notation is a mathematical notation that describes the limiting behavior of a function when the argument tends towards a particular value or infinity.
- Wikipedia
```

Certain operations can be more or less costly depending on what **data structure** we use.

Let's take a look at an **array** for example:

It will be super fast to access an array element by its index. However, **arrays** have **fixed-length**. So if we want to add or remove elements from them, they have to get **resized**. This will not **scale** well as the **size** of an array grows **very large**.

So for this particular problem, it's better to use another data structure called **Linked List**.
**Linked List** data structure can grow or shrink very quickly, but accessing a linked list element by its index is slow.

Let's try to describe the performance of an algorithm. That way we will get a better understanding of **Big O Notation**.

## Print Example

The first example in our Java Program will take an array of integers and print the first element on the console. In this case, it does not matter how big will be the array since we will print out only the first element. We can have an array with 1 element or 100000 elements. 

The method will have a single operation and takes a **constant** amount of time to run.
We will represent this using the **Big O** of 1. This is the run time complexity of this one example.

**Constant time simply means that regardless of the size of the input to a function, the cost always remains the same.**

As we said before, the size of our input does not matter for this example. The method will **always run on constant time** or **Big O of 1** 

```
public class Main {
        public void print(int[] numbers) {
            // 0(1) 
            System.out.println(numbers[0]);
        }
}
```

If we add one more operation and duplicate the printing line we will have 2 operations that are running in **constant time**.
The **runtime complexity** of this method will be **Big O of 2**. 


```
  public void print(int[] numbers) {
            // 0(2)
            System.out.println(numbers[0]);
            System.out.println(numbers[0]);
        }
```

We need to know how much an algorithm slows down as the input grows larger, so in this example whatever we have 1 or 100000 items our method will run **constant time**. 
So, we can simplify this and write down **0 of 1**

```
public class Main {
        public void print(int[] numbers) {
            // 0(1)
            System.out.println(numbers[0]);
            System.out.println(numbers[0]);
        }

}
```
## Loops Example

In the next example, we will take a look at a slightly more complex operation using **loops**.

```
public class Loop {
    public void print(int[] numbers) {
        for (int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }
    }
}
```

We are iterating all elements (numbers) of the array and print them on the console.

In this case, the size of the input matters because, if we have a single item in the array, we will have 1 operation.
if we have 100 000 items, for example, we will have 100 000 print operations.

We can say that the **cost of this algorithm grows linearly and in direct correlation to the size of the input**.
We represent that using a **Big O of N**.
**N** is the size of the input in this case.

It does not matter what kind of loop we are using for this. We can also use a for-each loop and the result will be the same.

An interesting case is if we have a print operation before and after the loop just like this:

```
 public void print(int[] numbers) {
        //0(n)
        System.out.println();
        for (int i = 0; i < numbers.length; i++) {
            System.out.println(numbers[i]);
        }
        System.out.println();
    }
```

As we said before, our single operations run out of **0(1)**, our loop operation runs of **0(n)**, and then once again, we will have **0(1)** because of the last print operation.

We can simply tell that our operation run of **0(2+n)**. // We just sum the complexity in this case //

```
 public void print(int[] numbers) {
        //0(2+n)
        System.out.println(); //0(1)
        for (int i = 0; i < numbers.length; i++) { //0(n)
            System.out.println(numbers[i]);
        }
        System.out.println();//0(1)
    }
```

However, when we use **Big O Notation** we drop the constants because they **do not really matter**. The reason for that is that imagine we have an array with 1 000 000 inputs.

Adding two extra operations doesn't change significantly the cost of our algorithm.

## Two Loops Example

Another case is if we have two loops inside our method.

```
public void print(int[] numbers) {
    // 0(2n)
    for (int i = 0; i < numbers.length; i++) {
        System.out.println(numbers[i]);
       }
    
    for (int i = 0; i < numbers.length; i++) {
        System.out.println(numbers[i]);
       }
    }

```

As you can tell, the complexity here will be **Big O of N + N** or **0(2n)**

## Two Inputs Example

This is another **case** where we **drop** the constant because all we need is an approximation of the cost of this algorithm relative to its input.
**2N** still represents a **linear growth**.

We can apply the same logic if we have two parameters in our method instead of 1.

If we have an `int[]` and `String[]`, we will have to deal with two inputs. We have to distinguish between those two inputs.
Using **n** for the size of the first input and **m** for the size of the second.

So the runtime complexity of this method will be **0(n+m)**. We can once again simplify and say that the complexity is **0(n)** because the runtime increases **linearly**.

// TODO: Nested Loops