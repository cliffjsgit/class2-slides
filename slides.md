---
title: 'Class 2: Python Review'
separator: '\-\-\-\-\-'
verticalSeparator: '\+\+\+\+\+'
theme: 'moon'
revealOptions:
    transition: 'fade'
---

### ITSE-1402 Intermediate Python
<span style="font-family:Helvetica Neue; font-weight:bold; color:#e49436">Class 2: Python Review</span>
<br /><br />
##### [https://bit.ly/1402-class2](https://bit.ly/1402-class2)

-----

##### Python Review

![Image](./assets/python.png)

##### Caption: "I wrote 20 short programs in Python yesterday.  It was wonderful.  Perl, I'm leaving you." - via [xkcd](https://xkcd.com/353/)

+++++

[https://bit.ly/1402-review](https://bit.ly/1402-review)

Note:
Let's get the review repo cloned in. 

-----

### Chapter 1 - The Way of the Program

+++++

### Exercise 1-1

Note:
We'll start off our review with some basic review of syntax.

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. In a print statement, what happens if you leave out 
# one of the parentheses, or both?
</code></pre>

Note:
There is a couple different ways this can play out depending on how you interpret it. 

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. In a print statement, what happens if you leave out
# one of the parentheses, or both?

print'test')
# One parenthesis:
#   File "<stdin>", line 1
#        print'test')
#                  ^
#   SyntaxError: invalid syntax

print 'test'
# Both parentheses (or space and one missing parenthesis):
#   File "<stdin>", line 1
#       print 'test'
#                   ^
#   SyntaxError: Missing parentheses in call to 'print'
</code></pre>

Note:
The difference is in the first part of the question. If you do space and one parenthesis, you get the same answer as the second.

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. If you are trying to print a string, what happens if
# you leave out one of you leave out one of the quotation
# marks, or both?
</code></pre>

Note:
Does this one have a similar property to the one before? Or will the answer be the same both ways?

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. If you are trying to print a string, what happens if
# you leave out one of you leave out one of the quotation
# marks, or both?

print('test)
# One quotation
#     File "<stdin>", line 1
#      print('test)
#                   ^
#    SyntaxError: EOL while scanning string literal

print(test)
# Both Quotations
#   Traceback (most recent call last):
#     File "<stdin>", line 1, in <module>
#   NameError: name 'test' is not defined
</code></pre>

Note:
Unlike the other example either parenthesis left out leads to the same result. 

+++++

#### Question 3

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. You can use a minus sign to make a negative number like -2. 
# What happens if you put a plus sign before a number? What
# about 2++2?
</code></pre>
+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. You can use a minus sign to make a negative number like -2. 
# What happens if you put a plus sign before a number? What
# about 2++2?

# -2 == -2
# +2 == +2
# 2++2 == 4
</code></pre>

+++++

#### Question 4

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. In math notation, leading zeros are okay, as in 02. What
# happens if you try this in Python?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. In math notation, leading zeros are okay, as in 02. What
# happens if you try this in Python?

# 02
#     File "<stdin>", line 1
#       02
#        ^
#   SyntaxError: invalid token
</code></pre>

Note:
In python2 the leading zero makes python interpret it as octal. In python3, it results in a syntax error. 

+++++

#### Question 5

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 5. What happens if you have two values with no operator between them?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 5. What happens if you have two values with no operator between them?

# No space
#   Traceback (most recent call last):
#     File "<stdin>", line 1, in <module>
#   NameError: name 'ab' is not defined

# Space
#     File "<stdin>", line 1
#       a b
#         ^
#     SyntaxError: invalid syntax
</code></pre>

Note:
Obviously 2 numbers next to each other makes whatver number it is. 5 and 5 = 55. When you do it with two variables, we get different results.

+++++

### Exercise 1-2

Note:
This time we are using the interpreter as a calculator just to see how python works with mathematical expressions (and stretch our brain muscles).

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. How many seconds are there in 42 minutes 42 seconds?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. How many seconds are there in 42 minutes 42 seconds?
x = (42*60)+42
print(x)
# 2562
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. How many miles are there in 10 kilometers? Hint: there are 
# 1.61 kilometers in a mile.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. How many miles are there in 10 kilometers? Hint: there are 
# 1.61 kilometers in a mile.
x = 10/1.61
print(x)
# 6.211180124223602
</code></pre>

Note:
This is a little messy, so we can clean it up with format.

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. How many miles are there in 10 kilometers? Hint: there are 
# 1.61 kilometers in a mile.
x = 10/1.61
print('{:03.2f}'.format(x))
# 6.21dd
</code></pre>

Note:
In short, this specifies the precision for floating point numbers. It's specifying that we want at least 3 numbers, with two trailing after the decimal. 
https://pyformat.info/ is your friend when it comes to these formats. We'll also talk about them more later.
+++++

#### Question 3

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. If you run a 10 kilometer race in 42 minutes 42 seconds, what 
# is your average pace (time per mile in minutes and seconds)? What
# is your average speed in miles per hour?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. If you run a 10 kilometer race in 42 minutes 42 seconds, what 
# is your average pace (time per mile in minutes and seconds)? What
# is your average speed in miles per hour?

answer1=((42*60)+42)/(10/1.61)/60
answer2=60/answer1
print("Min per mile:\t{:03.2f}\nMPH:\t\t{:03.2f}\n".format(answer1,answer2))  
</code></pre>

Note: We start with our the answer to question 1. Divide that by the answer to question 2. Then we divide that by 60 to get our minutes per mile. For the miles per hour, we divide 60 by the minutes per mile.

-----

### Chapter 2 - Variables, expressions, and statements

+++++

### Exercise 2-1

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. We've seen that n = 42 is legal. What about 42 = n?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. We've seen that n = 42 is legal. What about 42 = n?

# >>> 42 = n
#   File "<stdin>", line 1
# SyntaxError: can't assign to literal
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. How about x = y = 1?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. How about x = y = 1?

x=y=1
answer1=x  # 1
answer2=y  # 1
</code></pre>

+++++

#### Question 3

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. In some languages every statement ends with a semicolon, ;. What 
# happens if you put a semicolon at the end of a Python statement? 
# (print some arbitrary value assigned with ';' at the end)
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. In some languages every statement ends with a semicolon, ;. What 
# happens if you put a semicolon at the end of a Python statement? 
# (print some arbitrary value assigned with ';' at the end)

print(4); # Success!
</code></pre>

+++++

#### Question 4

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. What if you put a period at the end of a statement?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. What if you put a period at the end of a statement?

print(4). # SyntaxError: invalid syntax
</code></pre>

+++++

### Exercise 2-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1.The volume of a sphere with radius r is (4/3)pir^3. What is the 
# volume of a sphere with radius 5?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1.The volume of a sphere with radius r is (4/3)pir^3. What is the 
# volume of a sphere with radius 5?

from math import pi
answer1=(4.0/3.0)*pi*(5**3)   # 523.5987755982989
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Suppose the cover price of a book is $24.95, but bookstores 
# get a 40% discount. Shipping costs $3 for the first copy and 75 
# cents for each additional copy. What is the total wholesale cost
# for 60 copies?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Suppose the cover price of a book is $24.95, but bookstores 
# get a 40% discount. Shipping costs $3 for the first copy and 75 
# cents for each additional copy. What is the total wholesale cost
# for 60 copies?

answer1=24.95*0.6*60+0.75*(60-1)+3   # 945.4499999999999
</code></pre>

+++++

#### Question 3

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. If I leave my house at 6:52 am and run 1 mile at an easy pace   
# (8:15 per mile), then 3 miles at tempo (7:12 per mile) and 1 mile
# at an easy pace again, what time do I get home for breakfast?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. If I leave my house at 6:52 am and run 1 mile at an easy pace   
# (8:15 per mile), then 3 miles at tempo (7:12 per mile) and 1 mile
# at an easy pace again, what time do I get home for breakfast?

start = (6*60+52)*60
easy = (8*60+15)*2
fast = (7*60+12)*3
finish_hour = (start + easy + fast)/(60*60.0)
finish_floored = (start + easy + fast)//(60*60)
finish_minute  = (finish_hour - finish_floored)*60
answer1="{:02d}:{:02d}".format(finish_floored,finish_minute)  # 7:30
</code></pre>

-----

### Chapter 3 - Functions

+++++

### Exercise 3-1

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Write a function named right_justify that takes a string named  
# s as a parameter and prints the string with enough leading spaces  
# so that the last letter of the string is in column 70 of the display.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Write a function named right_justify that takes a string named  
# s as a parameter and prints the string with enough leading spaces  
# so that the last letter of the string is in column 70 of the display.

def right_justify(rstr):
    return ' ' * (70 - len(rstr)) + rstr
answer1=right_justify("monty") # 
</code></pre>

Note:
Can be done with format: 
return "{0:>70}".format(rstr)

+++++

### Exercise 3-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A function object is a value you can assign to a variable or pass   
# as an argument. For example, do_twice is a function that takes a 
# function object as an argument and calls it twice:
#
# def do_twice(f):
#     f()
#     f()
#
# Here's an example that uses do_twice to call a function named  
# print_spam twice:
#
# def print_spam():
#     print('spam')
#     do_twice(print_spam)
#
# Question 1
# 1. Type this example into a script and test it.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A function object is a value you can assign to a variable or pass   
# as an argument. For example, do_twice is a function that takes a 
# function object as an argument and calls it twice:
#
# def do_twice(f):
#     f()
#     f()
#
# Here's an example that uses do_twice to call a function named  
# print_spam twice:
#
# def print_spam():
#     print('spam')
#     do_twice(print_spam)
#
# Question 1
# 1. Type this example into a script and test it.

def do_twice(f):
    f()
    f()
def print_spam():
    print('spam')
    do_twice(print_spam)
print_spam()
# This function causes an infinite loop
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Modify do_twice so that it takes two arguments, a function 
# object and a value, and calls the function twice, passing the  
# value as an argument.
#
# Hint: you will need rename the function to "do_twice_2"
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Modify do_twice so that it takes two arguments, a function 
# object and a value, and calls the function twice, passing the  
# value as an argument.
#
# Hint: you will need rename the function to "do_twice_2"

def do_twice2(f,v):
    f(v)
    f(v)
</code></pre>

+++++

#### Question 3

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. Copy the definition of print_twice from earlier in this chapter  
# to your script.
#
# def print_twice(bruce):
#     print(bruce)
#     print(bruce)
#
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. Copy the definition of print_twice from earlier in this chapter  
# to your script.

def do_twice2(f,v):
    f(v)
    f(v)

def print_twice(bruce):
    print(bruce)
    print(bruce)
</code></pre>

+++++

#### Question 4

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. Use the modified version of do_twice to call print_twice twice,  
# passing 'spam' as an argument.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 4. Use the modified version of do_twice to call print_twice twice,  
# passing 'spam' as an argument.

def do_twice2(f,v):
    f(v)
    f(v)

def print_twice(bruce):
    print(bruce)
    print(bruce)

do_twice2(print_twice,"spam") # prints spam four times
</code></pre>

+++++

#### Question 5

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 5. Define a new function called do_four that takes a function object  
# and a value and calls the function four times, passing the value as  
# a parameter. There should be only two statements in the body of this
# function, not four.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 5. Define a new function called do_four that takes a function object  
# and a value and calls the function four times, passing the value as  
# a parameter. There should be only two statements in the body of this
# function, not four.

def do_twice2(f,v):
    f(v)
    f(v)

def print_twice(bruce):
    print(bruce)
    print(bruce)

def do_four(f,v):
    do_twice2(f,v)
    do_twice2(f,v)

do_four(print_twice,"spam")   # print spam 8 times
</code></pre>

+++++

### Exercise 3-3

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Write a function that draws a grid like the following:
#
# + - - - - + - - - - +
# |         |         |
# |         |         |
# |         |         |
# |         |         |
# + - - - - + - - - - + 
# |         |         | 
# |         |         | 
# |         |         |
# |         |         | 
# + - - - - + - - - - +
</code></pre>

Note:
Focus only on using methods we've talked about so far. Namely print and recursive fuctions

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Write a function that draws a grid like the following:
#
# + - - - - + - - - - +
# |         |         |
# |         |         |
# |         |         |
# |         |         |
# + - - - - + - - - - + 
# |         |         | 
# |         |         | 
# |         |         |
# |         |         | 
# + - - - - + - - - - +

def print_four(v):
    print(v)
    print(v)
    print(v)
    print(v)
def draw_grid():
    inter=('+ ' + '- ' * 4) * 2 + '+'
    line='|         |         |'
    print(inter)
    print_four(line)
    print(inter)
    print_four(line)
    print(inter)

draw_grid()
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that draws a similar grid with four rows and four 
# columns.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that draws a similar grid with four rows and four 
# columns.

def draw_double_grid():
    inter=('+ ' + '- ' * 4) * 4 + '+'
    line='|         |         |         |         |'
    print(inter)
    print_four(line)
    print(inter)
    print_four(line)
    print(inter)
    print_four(line)
    print(inter)
    print_four(line)
    print(inter)
draw_double_grid()
</code></pre>

-----

### Chapter 5 - Conditionals and Recursion

+++++

### Exercise 5-1

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# The time module provides a function, also named time, that 
# returns the current Greenwich Mean Time in "the epoch", which
# is an arbitrary time used as a reference point. On UNIX systems,
# the epoch is 1 January 1970.
#
# >>> import time
# >>> time.time()
#     1437746094.5735958
#
# Question 1
# 1. Write a script that reads the current time and converts it
# to a time of day in hours, minutes, and seconds, plus the number
# of days since the epoch.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# The time module provides a function, also named time, that 
# returns the current Greenwich Mean Time in "the epoch", which
# is an arbitrary time used as a reference point. On UNIX systems,
# the epoch is 1 January 1970.
#
# >>> import time
# >>> time.time()
#     1437746094.5735958
#
# Question 1
# 1. Write a script that reads the current time and converts it
# to a time of day in hours, minutes, and seconds, plus the number
# of days since the epoch.

import time
epoch = time.time()
# epoch // seconds_in_a_day
days_since_epoch = int(epoch // (24 * 60 * 60))
# (epoch % seconds_in_a_day) // seconds_in_an_hour
hours = int(epoch % (24 * 60 * 60) // 3600)
# (epoch % seconds_in_a_day) % seconds_in_an_hour // seconds_in_a_minute
minutes = int(epoch % (24 * 60 * 60) % 3600 // 60)
# (epoch % seconds_in_a_day) % seconds_in_an_hour % seconds_in_a_minute
seconds = int(epoch % (24 * 60 * 60) % 3600 % 60)
answer1="{:02d}:{:02d}:{:02d}".format(hours,minutes,seconds)
answer2=days_since_epoch
print("Time (GMT): {}\n".format(answer1)+
      "Days Since epoch: {}".format(answer2))
</code></pre>

+++++

### Exercise 5-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Fermat's Last Theorem says that there are no positive integers
# a, b, and c such that 
#
# a^n + b^n = c^n
# 
# for any values of n greater than 2.
#
# 1. Write a function named check_fermat that takes four parameters 
# a, b, c and n and checks to see if Fermat's theorem holds. If n
# is greater than 2 and a^n + b^n = c^n the program should print,
# "Holy smokes, Fermat was wrong!" Otherwise the program should 
# print, "No, that doesn't work."

</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Fermat's Last Theorem says that there are no positive integers
# a, b, and c such that 
#
# a^n + b^n = c^n
# 
# for any values of n greater than 2.
#
# 1. Write a function named check_fermat that takes four parameters 
# a, b, c and n and checks to see if Fermat's theorem holds. If n
# is greater than 2 and a^n + b^n = c^n the program should print,
# "Holy smokes, Fermat was wrong!" Otherwise the program should 
# print, "No, that doesn't work."

def check_fermat(a,b,c,n):
      if n > 2 and (a**n + b**n == c**n):
            print("Holy Smokes, Fermat was wrong!")
      else:
            print("No, that doesn't work.")
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that prompts the user to input values for a,
# b, c and n, converts them to integers, and uses check_fermat to
# check whether they violate Fermat's theorem.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that prompts the user to input values for a,
# b, c and n, converts them to integers, and uses check_fermat to
# check whether they violate Fermat's theorem.

def ask_fermat():
      a = input("a: ")
      b = input("b: ")
      c = input("c: ")
      n = input("n: ")
    
      check_fermat(int(a), int(b), int(c), int(n))
ask_fermat()
</code></pre>

+++++

### Exercise 5-3

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# If you are given three sticks, you may or may not be able
# to arrange them in a triangle. For example, if one of the
# sticks is 12 inches long and the other two are one inch long,
# you will not be able to get the short sticks to meet in the 
# middle. For any three lengths, there is a simple test to see
# if it is possible to form a triangle:
#
#     If any of the three lengths is greater than the sum of the
#     other two, then you cannot form a triangle. Otherwise, you
#     can. (If the sum of two lengths equals the third, they form
#     what is called a "degenerate" triangle.)"
#
# 1. Write a function named is_triangle that takes three integers
# as arguments, and that prints either "Yes" or "No", depending on
# whether you can or cannot form a triangle from sticks with the 
# given lengths
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# If you are given three sticks, you may or may not be able
# to arrange them in a triangle. For example, if one of the
# sticks is 12 inches long and the other two are one inch long,
# you will not be able to get the short sticks to meet in the 
# middle. For any three lengths, there is a simple test to see
# if it is possible to form a triangle:
#
#     If any of the three lengths is greater than the sum of the
#     other two, then you cannot form a triangle. Otherwise, you
#     can. (If the sum of two lengths equals the third, they form
#     what is called a "degenerate" triangle.)"
#
# 1. Write a function named is_triangle that takes three integers
# as arguments, and that prints either "Yes" or "No", depending on
# whether you can or cannot form a triangle from sticks with the 
# given lengths

def is_triangle(x,y,z):
    if x > y + z or y > x + z or z > x + y:
        print("No")
    else:
        print("Yes")
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that prompts the user to input three
# stick lengths, converts them to integers, and uses 
# is_triangle to check whether sticks with the given
# lengths can form a triangle.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. Write a function that prompts the user to input three
# stick lengths, converts them to integers, and uses 
# is_triangle to check whether sticks with the given
# lengths can form a triangle.

def ask_triangle():
    a = input("Type length of side a: ")
    b = input("Type length of side b: ")
    c = input("Type length of side c: ")
    
    is_triangle(int(a), int(b), int(c))
answer1=ask_triangle()

</code></pre>

+++++

### Exercise 5-4

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. What is the output of the following program? Draw a stack
# diagram that shows the state of the program when it prints
# the result.
#
# def recurse(n, s):
#    if n == 0:
#        print(s)
#    else:
#        recurse(n-1, n+s) 
# recurse(3, 0)
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. What is the output of the following program? Draw a stack
# diagram that shows the state of the program when it prints
# the result.
#
# def recurse(n, s):
#    if n == 0:
#        print(s)
#    else:
#        recurse(n-1, n+s) 
# recurse(3, 0)

"""
recurse:
    n -> 3
    s -> 0
recurse:
    n -> 2
    s -> 3
recurse:
    n -> 1
    s -> 5
recurse:
    n -> 0
    s -> 6

Program prints:
6   
"""
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. What would happen if you called this function like this:
# recurse(-1, 0)?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 2. What would happen if you called this function like this:
# recurse(-1, 0)?

# Continues infinitely
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. Write a docstring that explains everything someone would
# need to know in order to use this function (and nothing else).
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 3. Write a docstring that explains everything someone would
# need to know in order to use this function (and nothing else).

"""
computes value of s
n -> any positive integer
s -> any integer
"""
</code></pre>

-----

### Chapter 6 - Fruitful Functions

+++++

### Exercise 6-1

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Draw a stack diagram for the following program. What does
# the program print?
#
# def b(z):
#     prod = a(z, z)
#     print(z, prod)
#     return prod
#
# def a(x, y):
#     x = x + 1
#     return x * y
#
# def c(x, y, z):
#     total = x + y + z
#     square = b(total)**2
#     return square
#
# x = 1
# y = x + 1
# print(c(x, y+3, x+y))
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Draw a stack diagram for the following program. What does
# the program print?
#
# def b(z):
#     prod = a(z, z)
#     print(z, prod)
#     return prod
#
# def a(x, y):
#     x = x + 1
#     return x * y
#
# def c(x, y, z):
#     total = x + y + z
#     square = b(total)**2
#     return square
#
# x = 1
# y = x + 1
# print(c(x, y+3, x+y))

"""
main:
    x -> 1
    y -> 2
c:
    x -> 1
    y -> 5
    z -> 3
    total ---> 9
    square ---> 8100
b:
    z -> 9
    prod -> 90
a:
    x -> 9
    y -> 9
    x -> 10
 
Prints:
(9, 90)
8100   
"""
</code></pre>

+++++

### Exercise 6-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Question 1
# 1. The Ackermann function, A(m, n), is defined:
#
#    https://en.wikipedia.org/wiki/Ackermann_function
#
# Write a function named ack that evaluates the Ackermann
# function. Use your function to evaluate ack(3, 4),
# which should be 125. What happens for larger values
# of m and n?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# Question 1
# 1. The Ackermann function, A(m, n), is defined:
#
#    https://en.wikipedia.org/wiki/Ackermann_function
#
# Write a function named ack that evaluates the Ackermann
# function. Use your function to evaluate ack(3, 4),
# which should be 125. What happens for larger values
# of m and n?

def ack(m, n):
    if m == 0:
        return n + 1
    elif m > 0 and n == 0:
        return ack(m - 1, 1)
    elif m > 0 and n > 0:
        return ack(m - 1, ack(m, n - 1))
answer1 = ack(3, 4)
</code></pre>

+++++

### Exercise 6-3

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A palindrome is a word that is spelled the same backward and 
# forward, like  "noon" and "redivider". Recursively, a word is 
# a palindrome if the first and last letters are the same and the 
# middle is a palindrome.
#
# The following are functions that take a string argument and
# return the first, last, and middle letters:
#
# def first(word):
#     return word[0]
#      
# def last(word):
#     return word[-1]
#
# def middle(word):
#     return word[1:-1]
#
# We'll see how they work in Chapter 8.
#
# This allows you to use the functions from palindrome.py for the
# two questions.
#
import palindrome
#
# Question 1
# 1. Type these functions into a file named palindrome.py and 
# test them out. What happens if you call middle with a string
# with two letters? One letter? What about the empty string,
# which is written '' and contains no letters?
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A palindrome is a word that is spelled the same backward and 
# forward, like  "noon" and "redivider". Recursively, a word is 
# a palindrome if the first and last letters are the same and the 
# middle is a palindrome.
#
# The following are functions that take a string argument and
# return the first, last, and middle letters:
#
# def first(word):
#     return word[0]
#      
# def last(word):
#     return word[-1]
#
# def middle(word):
#     return word[1:-1]
#
# We'll see how they work in Chapter 8.
#
# This allows you to use the functions from palindrome.py for the
# two questions.
#
import palindrome
#
# Question 1
# 1. Type these functions into a file named palindrome.py and 
# test them out. What happens if you call middle with a string
# with two letters? One letter? What about the empty string,
# which is written '' and contains no letters?

# It prints an empty string.
</code></pre>

+++++

#### Question 2

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

import palindrome

# 2. Write a function called is_palindrome that takes a string
# argument and returns True if it is a palindrome and False
# otherwise. Remember that you can use the built-in function 
# len to check the length of a string.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

import palindrome

# 2. Write a function called is_palindrome that takes a string
# argument and returns True if it is a palindrome and False
# otherwise. Remember that you can use the built-in function 
# len to check the length of a string.

def is_palindrome(word):
    if len(word) <= 1:
        return True
    elif palindrome.first(word) == palindrome.last(word):
        if len(palindrome.middle(word)) == 1:
            return True
        else:
            return is_palindrome(palindrome.middle(word))
    else:
        return False
</code></pre>

+++++

### Exercise 6-4

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. A number, a, is a power of b if it is divisible by b and a/b
# is a power of b. Write a function called is_power that takes 
# parameters a and b and returns True if a is a power of b. 
# Hint: you will have to think about the base case.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. A number, a, is a power of b if it is divisible by b and a/b
# is a power of b. Write a function called is_power that takes 
# parameters a and b and returns True if a is a power of b. 
# Hint: you will have to think about the base case.

def is_power(a, b):
    if a == b:
        return True
    elif a%b == 0:
        return is_power(a/b, b)
    else:
        return False
</code></pre>

+++++


### Exercise 6-5

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The greatest common divisor (GCD) of a and b is the
# largest number that divides both of them with no remainder.
# One way to find the GCD of two numbers is based on the 
# observation that if r is the remainder when a is divided by b,
# then gcd(a, b) = gcd(b, r). As a base case, we can use gcd
# (a, 0) = a.
#
# Write a function called gcd that takes parameters a and b
# and returns their greatest common divisor.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The greatest common divisor (GCD) of a and b is the
# largest number that divides both of them with no remainder.
# One way to find the GCD of two numbers is based on the 
# observation that if r is the remainder when a is divided by b,
# then gcd(a, b) = gcd(b, r). As a base case, we can use gcd
# (a, 0) = a.
#
# Write a function called gcd that takes parameters a and b
# and returns their greatest common divisor.

def gcd(a, b):
    if b == 0:
        return a
    return gcd(b, a % b) 
</code></pre>

-----

### Chapter 7 - Iteration

+++++

### Exercise 7-1

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Copy the loop from Section 7.5 and encapsulate it in a 
# function called mysqrt that takes a as a parameter, chooses
# a reasonable value of x, and returns an estimate of the square
# root of a.
#
# To test it, write a function named test_square_root that 
# prints table like this:
#
# a   mysqrt(a)      math.sqrt(a)   diff
# _   _________      ____________   ____
# 1.0 1.0            1.0            0.0
# 2.0 1.41421356237  1.41421356237  2.22044604925e-16
# 3.0 1.73205080757  1.73205080757  0.0
# 4.0 2.0            2.0            0.0
# 5.0 2.2360679775   2.2360679775   0.0
# 6.0 2.44948974278  2.44948974278  0.0
# 7.0 2.64575131106  2.64575131106  0.0
# 8.0 2.82842712475  2.82842712475  4.4408920985e-16
# 9.0 3.0            3.0            0.0
#
# The first column is a number, a;
# the second column is the square root of a computed with mysqrt;
# the third column is the square root computed by math.sqrt;
# the fourth column is the absolute value of the difference
# between the two estimates.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. Copy the loop from Section 7.5 and encapsulate it in a 
# function called mysqrt that takes a as a parameter, chooses
# a reasonable value of x, and returns an estimate of the square
# root of a.
#
# To test it, write a function named test_square_root that 
# prints table like this:
#
# a   mysqrt(a)      math.sqrt(a)   diff
# _   _________      ____________   ____
# 1.0 1.0            1.0            0.0
# 2.0 1.41421356237  1.41421356237  2.22044604925e-16
# 3.0 1.73205080757  1.73205080757  0.0
# 4.0 2.0            2.0            0.0
# 5.0 2.2360679775   2.2360679775   0.0
# 6.0 2.44948974278  2.44948974278  0.0
# 7.0 2.64575131106  2.64575131106  0.0
# 8.0 2.82842712475  2.82842712475  4.4408920985e-16
# 9.0 3.0            3.0            0.0
#
# The first column is a number, a;
# the second column is the square root of a computed with mysqrt;
# the third column is the square root computed by math.sqrt;
# the fourth column is the absolute value of the difference
# between the two estimates.
#
# pip3 install prettytable

def mysqrt(a):
    x = 0.5 * a
    while True:
        estimated_root = 0.5 * (x + a/x)
        if estimated_root == x:
            return estimated_root
        x = estimated_root

def test_square_root(list_of_a):
    import math
    from prettytable import PrettyTable
    t = PrettyTable(['a', 'mysqrt(a)','math.sqrt(a)','diff'])
    
    for a in list_of_a:
        col1 = float(a)
        col2 = mysqrt(a)
        col3 = math.sqrt(a)
        col4 = abs(mysqrt(a) - math.sqrt(a))
        t.add_row([col1,col2,col3,col4])
    print(t)

test_square_root(range(1,10))
</code></pre>

+++++

### Exercise 7-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# The built-in function eval takes a string and evaluates it
# using the Python interpreter. For example:
#
# >>> eval('1 + 2 * 3')
# 7
# >>> import math
# >>> eval('math.sqrt(5)')
# 2.2360679774997898
# >>> eval('type(math.pi)')
# <class 'float'>
#
# Question 1
# 1. Write a function called eval_loop that iteratively prompts
# the, user takes the resulting input and evaluates it using
# eval, and prints the result. It should continue until the user
# enters 'done', and then return the value of the last expression
# it evaluated.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# The built-in function eval takes a string and evaluates it
# using the Python interpreter. For example:
#
# >>> eval('1 + 2 * 3')
# 7
# >>> import math
# >>> eval('math.sqrt(5)')
# 2.2360679774997898
# >>> eval('type(math.pi)')
# <class 'float'>
#
# Question 1
# 1. Write a function called eval_loop that iteratively prompts
# the, user takes the resulting input and evaluates it using
# eval, and prints the result. It should continue until the user
# enters 'done', and then return the value of the last expression
# it evaluated.

def eval_loop():
    import math
    while True:
        n = raw_input('>>> ')
        if n == 'done':
            break
        else:
            result = eval(n)
            print(result)
    print(result)

eval_loop()
</code></pre>

+++++

### Exercise 7-3

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The mathematician Srinivasa Ramanujan found an infinite
# series that can be used to generate a numerical 
# approximation of 1/pi.
#
# https://en.wikipedia.org/wiki/Pi#Rapidly_convergent_series
#
# Write a function called estimate_pi that uses this formula
# to compute and return an estimate of pi. It should use a 
# while loop to compute terms of the summation until the 
# last term is smaller than 1e-15 (which is Python notation 
# for 10**-15).
#
# You can check the result by comparing it to math.pi.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The mathematician Srinivasa Ramanujan found an infinite
# series that can be used to generate a numerical 
# approximation of 1/pi.
#
# https://en.wikipedia.org/wiki/Pi#Rapidly_convergent_series
#
# Write a function called estimate_pi that uses this formula
# to compute and return an estimate of pi. It should use a 
# while loop to compute terms of the summation until the 
# last term is smaller than 1e-15 (which is Python notation 
# for 10**-15).
#
# You can check the result by comparing it to math.pi.

import math

def factorial(n):
    if n == 0:
        return 1
    else:
        recurse = factorial(n-1)
        result = n * recurse
        return result
        
def estimate_pi():
    total = 0
    k = 0
    factor = 2 * math.sqrt(2) / 9801
    while True:
        num = factorial(4*k) * (1103 + 26390*k)
        den = factorial(k)**4 * 396**(4*k)
        term = factor * num / den
        total += term
        
        if abs(term) < 1e-15:
            break
        k += 1

    return 1 / total

print(estimate_pi())
</code></pre>

-----

### Chapter 8 - Strings

+++++

### Exercise 8-2

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. There is a string method called count that is similar to the  
# function in Section 8.7. Read the documentation of this method  
# and write an invocation that counts the number of a's in 'banana'.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. There is a string method called count that is similar to the  
# function in Section 8.7. Read the documentation of this method  
# and write an invocation that counts the number of a's in 'banana'.

word = 'banana'
print(word.count('a'))   # 3
</code></pre>

+++++

### Exercise 8-3

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. A string slice can take a third index that specifies the
# "step size"; that is, the number of spaces between successive
# characters. A step size of 2 means every other character; 3
# means every third, etc.
#
# >>> fruit = 'banana'
# >>> fruit[0:5:2]
# 'bnn'
#
# A step size of -1 goes through the word backwards, so the
# slice [::-1] generates a reversed string. Use this idiom
# to write a one-line version of is_palindrome from Exercise 
# 6.3.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. A string slice can take a third index that specifies the
# "step size"; that is, the number of spaces between successive
# characters. A step size of 2 means every other character; 3
# means every third, etc.
#
# >>> fruit = 'banana'
# >>> fruit[0:5:2]
# 'bnn'
#
# A step size of -1 goes through the word backwards, so the
# slice [::-1] generates a reversed string. Use this idiom
# to write a one-line version of is_palindrome from Exercise 
# 6.3.

def is_palindrome(word):
    return word == word[::-1]
</code></pre>

+++++

### Exercise 8-4

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The following functions are all INTENDED to check whether a
# string contains any lowercase letters, but at least some of them
# are wrong. For each function, describe what the function actually
# does (assuming that the parameter is a string).

def any_lowercase1(s):
    for c in s:
        if c.islower():
            return True
        else:
            return False
print(any_lowercase1("PooP"))

def any_lowercase2(s):
    for c in s:
        if 'c'.islower():
            return 'True'
        else:
            return 'False'

def any_lowercase3(s):
    for c in s:
        flag = c.islower()
    return flag

def any_lowercase4(s):
    flag = False
    for c in s:
        flag = flag or c.islower()
    return flag

def any_lowercase5(s):
    for c in s:
        if not c.islower():
            return False
    return True
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# 1. The following functions are all INTENDED to check whether a
# string contains any lowercase letters, but at least some of them
# are wrong. For each function, describe what the function actually
# does (assuming that the parameter is a string).

def any_lowercase1(s):
    # Checks only first letter in string if it is lowercase or not 
    # and returns boolean.
    for c in s:
        if c.islower():
            return True
        else:
            return False
print(any_lowercase1("PooP"))

def any_lowercase2(s):
    # Checks if string 'c' is lowercase or not; and returns string
    #  'True'; Returns 'True' everytime, given argument does not
    # matter;
    for c in s:
        if 'c'.islower():
            return 'True'
        else:
            return 'False'

def any_lowercase3(s):
    # Checks if each letter in string is lowercased or not and 
    # assigned the outcome (boolean value) to the variable 'flag'; 
    # new value is assigned to 'flag' with every checked letter;
    # Returns boolean value of calling islower() method on only 
    # the last letter of the given string;
    for c in s:
        flag = c.islower()
    return flag

def any_lowercase4(s):
    # Checks if there is ANY lowercased letter in given string
    # and returns boolean;
    flag = False
    for c in s:
        flag = flag or c.islower()
    return flag

def any_lowercase5(s):
    # Checks every letter if it is not lowercased and returns
    # boolean if all the letters in string are lowercased or not;
    for c in s:
        if not c.islower():
            return False
    return True
</code></pre>

+++++


### Exercise 8-5

Note:

+++++

#### Question 1

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A Caesar cypher is a weak form of encryption that involves 
# "rotating" each letter by a fixed number of places. To rotate a
# letter means to shift it through the alphabet, wrapping around to
# the beginning if necessary, so 'A' rotated by 3 is 'D' and 'Z'
# rotated by 1 is 'A'. To rotate a word, rotate each letter by the
# same amount. For example, "cheer" rotated by 7 is "jolly" and 
# "melon" rotated by -10 is "cubed". In the movie 2001: A Space 
# Odyssey, the ship computer is called HAL, which is IBM rotated 
# by -1.
#
# Question 1
# 1. Write a function called rotate_word that takes a string and an
# integer as parameters, and returns a new string that contains the 
# letters from the original string rotated by the given amount.
#
# You might want to use the built-in function ord, which converts
# a character to a numeric code, and chr, which converts numeric codes
# to characters. Letters of the alphabet are encoded in alphabetical
# order, so for example:
#
# >>> ord('c') - ord('a')
# 2
#
# Because 'c' is the two-eth letter of the alphabet.
#
# But beware: the numeric codes for upper case letters are different.
#
# Potentially offensive jokes on the Internet are sometimes encoded
# in ROT13, which is a Caesar cypher with rotation 13. If you are 
# not easily offended, find and decode some of them.
</code></pre>

+++++

<pre class="stretch"><code class="python" data-trim data-noescape>
#!/usr/bin/env python3

# A Caesar cypher is a weak form of encryption that involves 
# "rotating" each letter by a fixed number of places. To rotate a
# letter means to shift it through the alphabet, wrapping around to
# the beginning if necessary, so 'A' rotated by 3 is 'D' and 'Z'
# rotated by 1 is 'A'. To rotate a word, rotate each letter by the
# same amount. For example, "cheer" rotated by 7 is "jolly" and 
# "melon" rotated by -10 is "cubed". In the movie 2001: A Space 
# Odyssey, the ship computer is called HAL, which is IBM rotated 
# by -1.
#
# Question 1
# 1. Write a function called rotate_word that takes a string and an
# integer as parameters, and returns a new string that contains the 
# letters from the original string rotated by the given amount.
#
# You might want to use the built-in function ord, which converts
# a character to a numeric code, and chr, which converts numeric codes
# to characters. Letters of the alphabet are encoded in alphabetical
# order, so for example:
#
# >>> ord('c') - ord('a')
# 2
#
# Because 'c' is the two-eth letter of the alphabet.
#
# But beware: the numeric codes for upper case letters are different.
#
# Potentially offensive jokes on the Internet are sometimes encoded
# in ROT13, which is a Caesar cypher with rotation 13. If you are 
# not easily offended, find and decode some of them.

def rotate_letter(letter, n):
    if letter.isupper():
        start = ord('A')
    elif letter.islower():
        start = ord('a')
    else:
        return letter

    c = ord(letter) - start
    i = (c + n) % 26 + start
    return chr(i)

def rotate_word(word, n):
    res = ''
    for letter in word:
        res += rotate_letter(letter, n)
    return res

print(rotate_word("cheer", 7))
print(rotate_word("IBM", -1))
</code></pre>