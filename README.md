# Common datastructures used in computer programming

Author: [John Francis](john9francis.github.io)

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
![Several unique rocks organized in a desk organizer](rock_collection.jpg)

Imagine you have a rock collection. You want to collect one rock of each type. If you find a new rock, and you already have one of that type, you don't need this new rock. This rock collection is like a set. 

A set is a list in which there is one rule:

1. Each value is unique.

So let's say you have a set including the values 1,2, and 3. If you try to add 1 to the set, it will ignore the addition because there is already a 1 in the set. So after the add attempt, your set will still only include 1,2, and 3. 

The purpose of sets is to be very efficient in adding and retrieving data. Another purpose is to find duplicates between data structures. 

### Hashing functions:

A very common practice when making sets is using hashing functions. Hashing functions make it possible for sets to be extremely efficient.

What a hashing function does is take in a non-integer data point, (Like a string, bool, or other object type) and turn it into a unique integer that can be put into a set. For example, a hashing function could turn the string "Hello World" into the code: "19482743." Then that integer can be stored in a set. 

### Adding to a set

In python, we can use the `set` keyword or curly braces `{}` to create a set.

```python
my_set = set()
# or
my_set = {}
```

To add to the set, you can use the keyword, "add" provided by python. 
```python
my_set.add(1)
```
If an integer is already found in the set, python will ignore a duplicate.
```python
my_set.add(1)
for x in my_set:
  print(x)
# output: 1

my_set.add(1)
my_set.add(1)
for x in my_set:
  print(x)
# output: 1
```

### Getting info from a set
You can't access a certain index of a set in python using the classic `list[i]` notation, however, you can quickly check if a value is found in the set. You can find a value by utilizing the "in" keyword.
```python
if x in my_set:
  print(x)
```
Another useful thing you can do in sets is detect identical entries in both sets. For example, if you run following python code, it will tell you which values are present in both sets.
```python
set1 = {1,2,3,4,5}
set2 = {3,4,5,6,7}

shared_values = set1 & set2

# display result
for x in shared_values:
  print(x)
# output: 3,4,5
```

### Performance

Hash values work almost like pointers, they are used to access a certain index in the set. Because of this, most set operations are O(1) performance. This is a great benefit of using sets, their excellent performance. 

### Conflicts

### Example

### Problem to solve

Write a function that takes in a list of strings, and use a set to check which words are in both lists. Return a list of only the words that are found in both lists. 

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
