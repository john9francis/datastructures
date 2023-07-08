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

Now I will go through and explain what happens in this code. First, a new stack is defined by `my_stack = []`. Then, 1 and 2 are added to the top of the stack. We then took 2 off the stack, leaving my_stack as just [1]. Then we added 3 on top, and 4 on top, making the stack [1,3,4]. Next, we removed the 4, and then removed the 3, lleaving the stack as [1]. 

Finally, we printed `my_stack.pop()` which does two things. First, it takes the 1 off the stack, leaving the stack empty. Second, it prints "1" because the pop() function returns what it popped. Finally, we print the length of the stack with `print(len(my_stack))`. which equals zero.

So the output should be:
```powershell
> 1
> 0
```

### Problem to solve

Write a python function called, "reverse_word" that takes in a string, and using stacks, reverses all the letters in the string. In other words, this should be the output:

```python
print(reverse_word('Hello World'))
```
```powershell
> dlroW olleH
```

[example solution](#example-solutions)

## Set 

### Introduction:

Imagine you are playing with some russian nesting dolls. Let's say they are labelled 1 through 10, with the smallest being labelled, "1," and the biggest being labelled, "10." These dolls are like a set. A set has two constraints: 

1. Is always in numerical order
2. Can only have one of each value

In the russian nesting dolls example, say you want to put 1, 3, and 10 together. You must put 1 inside of 3, and 3 inside of 10. You can't put 10 inside of 1, because the smaller one must go inside of the bigger one. This is similar to a set, because in a set you can't store the smaller numbers after the bigger numbers. Values in a set automatically get put in order smallest to largest.

If you have two russian nesting dolls that are the same size, and you want to put them all together, you can't include both the same-sized dolls in there, you must only have one for them to nicely fit inside of eachother. A set is like this as well, it only takes unique values. Since a set is automatically sorted in order, if there were two of the same number it wouldn't know which one to put first, or how to access the correct one later.

### Adding to a set


## Tree

## Example solutions
Example solution to the stack problem:
```python
def reverse_word(word):
  '''Takes in a word and returns the reverse of it'''

  # put the letters of the word into a stack
  word_stack = []
  for letter in word:
    word_stack.append(letter)

  # create a string for the new word
  new_word = ""

  # pop the letters off the end of the stack and add them to the new word string
  for i in range(len(word_stack)):
    new_word += word_stack.pop()

  return new_word
```
