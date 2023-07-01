# Common datastructures used in computer programming

Author: John Francis

Website: [John Francis](john9francis.github.io)

Date: 7/1/2023

There are several types of datastructures used in computer programming to store data. The most commonly known data structure is the list:
```python
my_list = [1,2,3]
```
However, there are many other structures including stack, queue, set, linked list, and tree, to name a few. Each data structure has it's own uses. Each has highest performance for it's specific situation. 

In this tutorial I will be going over the following data structures:

* [Stack](#stack)
* [Set](#set)
* [Tree](#tree)

## Stack
### Introduction
![stack of pancakes](stack.jpg)

Imagine you're making pancakes for breakfast. As you take each hot pancake off the pan, you place them on top of one another on a stack. Let's say you make 3 pancakes: first, you made pancake 1, then pancake 2, and finally pancake 3, placing them on the stack as you make them. Which pancake get's eaten first?

The pancake at the top of the stack, or the newest pancake (pancake 3) is eaten first. Then pancake 2 is eaten, and finally pancake 1 is eaten. The pancakes are eaten in the opposite order than the order they were placed in the stack.

In programming, a stack follows the same principle. 

In the stack programming data structure, you can't just get any index of the list, you can only access the "newest" item, or the latest one added to the stack. To uncover previous items, you must uncover them by taking things off of the stack. 

### Adding to a stack
In python, we would add to a stack by the following code:
```python
my_stack = []
my_stack.append('item one')
```
The "append" function in python puts something at the end of the list, or the top of the stack. 
### Getting info from a stack
In python, we would take the newest item from the stack with the following code:
```python
my_stack.pop()
```
"pop()" is a function in python that removes and returns the last item from the list. In the example of our stack, it would return the most-recently-added item. 

With these two functions, "append" and "pop," we have everything we need to manipulate a stack. 
### Performance
You may be wondering, why would I use a stack instead of a normal list? Well, one reason is that a stack has very good performance. If you are familiar with Big-O notation, many list operations can be O(n) or even O(n^2). On the other hand, stack operations are almost all just O(1). 

If you think about it, the computer doesn't have to do much to deal with a stack. No matter how big the stack is, you're only dealing with the last entry.

### Example
Here's an example of some stack operations. 
```python
my_stack = []
my_stack.append(1)
my_stack.append(2)
my_stack.pop()
my_stack.append(3)
my_stack.append(4)
my_stack.pop()
my_stack.pop()

print(my_stack.pop())
print(len(my_stack))
```
Try to predict what this code will output. 

### Problem to solve

## Set 

## Tree
