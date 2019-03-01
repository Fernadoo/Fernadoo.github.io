---
layout:     post
title:      Python review
subtitle:   小白请进
date:       2017-06-26
author:     Fernando
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - Python
---

# *Python Review* 
> for beginners

### 1. print()

* `print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)` to output something
	* by default:
		* with the separation of 
			```
				>>> print(1,'23asd',[1,2,3],(1,2))
				1 23asd [1, 2, 3] (1, 2)
			```
		* with the end of '\n'		
			```python
				>>> for i in range(1,4):
				...		print(i)
				...
				1
				2
				3
			```
		* ignore `file=sys.stdout, flush=False`
	* change the arguements
		* change the separation 
			```
				>>> print(1,'23asd',[1,2,3],(1,2), sep='\n')
				1
				23asd
				[1, 2, 3]
				(1, 2)	
			```
		* change the end
			```
				>>>	for i in range(1,4):
				...		print(i,end=' ')
				...
				1 2 3	
			```

* ***debug**: while facing with a great block of program without knowing what goes wrong, we add some `print()` to figure out which step produces problem
	 `help(print)` to get more info		

	

### 2. string(s)

* something enclosed with `"` or `'`
* operations:
	* `len(s)` to work out the length of s
		```
			>>> s='123sd67fhjk'
			>>> len(s)
			11
		```
	* `index` & `slice`
		* index: `s[i]` to enter the (i+1)th element of s
			```	
				>>> s[0]
				'1'
				>>> s[-1]
				'k'
			```
		* slice: `s[i:j:k]` to take out a slice starting with index i , ending up with index (j-1), with the step of k   
			```
				>>> s[1:10:3]
				'2df'
				>>> s[2:5]
				'3sd'
				>>> s[3:]
				'sd67fhjk'
				>>> s[:-4]
				'123sd67'
			```
		* does not support item assignment
			```	
				>>> s[2]=4
				Traceback (most recent call last):
					  File "<stdin>", line 1, in <module>
				TypeError: 'str' object does not support item assignment
			```
	* `s1 + s2` to produce an addition of s1 and s2
	* `str(a)` *where a is an int or float or list or tuple etc.* to transform a into 'a' with type `str`
	* `help(str)` to get more info
					

### 3. list(l) & tuple(t) 

* **list** (mutable)
	* elements enclosed with `[]`
	* elements can be `int` or `float` or `str` or `list` or `tuple` or `dict` *etc*. 
	* `len(l)` as string
		`index` and `slice` mostly as string	
		* support item assignment
			```
				>>> l=[1,2,3]
				>>> l[2]=5
				>>> l
				[1,2,5]
			```
	* `l.append(a)` to push a into l (and return None)
		```
			>>> l=[1,2,3]
			>>> l.append(5)
			>>> l
			[1,2,3,5]
			>>> l1=l.append(6)
			>>> print(l1)
			None
			```
	* `l.pop(i)` to pop out the ith element (and return it)
		```	
			>>> l=[1,2,3,4,5,6,7]
			>>> l.pop()
			7
			>>> l.pop(3)
			4
			>>> l
			[1,2,3,5,6]
		```
	* `l.reverse()` to return a reverse order of l
	* `l.sort()` to return l with an ascending order
	* `help(list)` to get more info
	
* **tuple** (immutable)
	* elements enclosed with `()`
	* elements can be `int` or `float` or `str` or `list` or `tuple` or `dict` *etc*. 
	* `len(l)` as string
	* `index` and `slice` as string
		* does not support item assignment
			```	
				>>> t=(1,2,3)
				>>> t[2]
				3
				>>> t[2]=4
				Traceback (most recent call last):
  				  File "<stdin>", line 1, in <module>
  				TypeError: 'tuple' object does not support item assignment
  			```
	* `help(tuple)` to get more info
	
***

***quick view***

|                   |str   |list|tuple|
|:-----------------:|:----:|:--:|:---:|
|**len( )**          |Yes   |Yes |Yes  |
|**index**          |Yes   |Yes |Yes  |
|**silce**          |Yes   |Yes |Yes  |
|**item assignment**|Nope  |Yes |Nope |
|**append( )**       |Nope  |Yes |Nope |
|**pop( )**          |Nope  |Nope|Nope |

***

### 4. dictionary(dict)

* click [Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries) and refer to Chap5.5
* `help(dict)` to get more info



### 5. Defining functions:

* click [defining functions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions) and refer to Chap4.6

### 6. for & while & if

* **for** 
	```
		>>> # Measure some strings:
		... words = ['cat', 'window', 'defenestrate']
		>>> for w in words:
		...     print(w, len(w))
		...
		cat 3
		window 6
		defenestrate 12
	```
* **while**
	```
		>>> a, b = 0, 1
		>>> while b < 1000:
		...     print(b, end=',')
		...     a, b = b, a+b
		...
		1,1,2,3,5,8,13,21,34,55,89,144,233,377,610,987,
	```
* **if**
	```
		>>> x = int(input("Please enter an integer: "))
		Please enter an integer: 42
		>>> if x < 0:
		...     x = 0
		...     print('Negative changed to zero')
		... elif x == 0:
		...     print('Zero')
		... elif x == 1:
		...     print('Single')
		... else:
		...     print('More')
		...
		More
	```

###7. break & continue
* **break** 
	```
		>>> for n in range(2, 10):
		...     for x in range(2, n):
		...         if n % x == 0:
		...             print(n, 'equals', x, '*', n//x)
		...             break
		...     else:
		...         # loop fell through without finding a factor
		...         print(n, 'is a prime number')
		...
		2 is a prime number
		3 is a prime number
		4 equals 2 * 2
		5 is a prime number
		6 equals 2 * 3
		7 is a prime number
		8 equals 2 * 4
		9 equals 3 * 3
	```
* **continue**
	```
		>>> for num in range(2, 10):
		...     if num % 2 == 0:
		...         print("Found an even number", num)
		...         continue
		...     print("Found a number", num)
		Found an even number 2
		Found a number 3
		Found an even number 4
		Found a number 5
		Found an even number 6
		Found a number 7
		Found an even number 8
		Found a number 9
	```
### 8. pass

######The pass statement does nothing.
	```
		>>> while True:
		...     pass  # Busy-wait for keyboard interrupt (Ctrl+C)
		...
		
		>>> def f(x):
		...     pass   # Remember to implement this!
		...
	```
### 9. other useful functions 

1. `*range()`
	```
		>>> for i in range(1,10,3):
		... 	print(i)
		...
		1
		4
		7
		>>> for i in range(3,6):
		... 	print(i)
		...
		3
		4
		5
		>>> for i in range(3):
		... 	print(i)
		...
		0
		1
		2
	```
	click [The range() Function](https://docs.python.org/3/tutorial/controlflow.html#the-range-function) and refer to Chap4.3
	
2. `*eavl()`
	```
		>>> s='123'
		>>> s=eval(s)
		>>> s
		123
		>>>
		>>> l='[1,2,3,4]'
		>>> l=eval(l)
		>>> l
		[1,2,3,4]
		>>>
		>>> t='(1,2,3)'
		>>> t=eval(t)
		>>> t
		(1,2,3)
		>>>
		>>> d='{1: 'a', 2: 'b'}'
		>>> d=eval(d)
		>>> d
		{1: 'a', 2: 'b'}
	```
	
3. `''.join()`
	```
		>>> l=['2','3','4','qwe','asd']
		>>> r='-enhhh-'.join(l)
		>>> r
		'2-enhhh-3-enhhh-4-enhhh-qwe-enhhh-asd'
	```

4. `split()`
	```
		>>> s='123|242|sdfsd'
		>>> l=s.split('|')
		>>> l #return a list
		['123', '242', 'sdfsd'] 
	```
5. `count()`
	```
		>>> l=['1','4','1']
		>>> l.count('1')
		2
	```

***

######**more info**: <zhufm@shanghaitech.edu.cn>

