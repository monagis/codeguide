# Zen of Python
Also known as PEP 20, are the guiding principles for Python's design.

```
1.  Beautiful is better than ugly.
2.  Explicit is better than implicit.
3.  Simple is better than complex.
4.  Complex is better than complicated.
5.  Flat is better than nested.
6.  Sparse is better than dense.
7.  Readability counts.
8.  Special cases aren't special enough to break the rules.
9.  Although practicality beats purity.
10. Errors should never pass silently.
11. Unless explicitly silenced.
12. In the face of ambiguity, refuse the temptation to guess.
12. There should be one-- and preferably only one --obvious way to do it.
14. Although that way may not be obvious at first unless you're Dutch.
15. Now is better than never.
16. Although never is often better than *right* now.
17. If the implementation is hard to explain, it's a bad idea.
18. If the implementation is easy to explain, it may be a good idea.
19. Namespaces are one honking great idea -- let's do more of those!
```

### Beatiful is better than ugly.
The goal here is to write programs for human readers.

```python
# ugly
halve_evens_only = lambda nums: map(lambda i: i/2, filter(lambda i: not i%2, nums))

# beautiful
def halve_evens_only(nums):
    return [i/2 for i in nums if not i % 2]
```


Consider the following javascript conditional in comparision to the python below it.
 The use of `and`, `or` instead of `&&`, `||` respectively. Though it is subjective, the code seems more readable and beautiful this way.

```javascript
// ugly
if (is_valid(a) && b == 0 || s == 'yes') {
```

versus

```python
# beautiful
if is_valid(a) and b == 0 or s == 'yes':
```

### Explicit is better than implicit.

Every time you invoke a function you should name its module explicitly:

```python
import os
print os.getcwd()
```

instead of

```python
from os import *
print getcwd()
```

### Simple is better than complex.
If the implementation is easy to explain, it may be a good idea.


### Complex is better than complicated.
Though the words means similar things, the sentiment here is:

*Complex* - Consisting of many different and connected parts. A lot of things going on.

*Complicated* - Difficult to understand.

To give a simple example:

```python
# complicated
counter = 0
while counter < 5:
   print counter
   counter += 1
```
The code is very easy to understand. It is not complex. However, it is complicated. You do not need to manually perform most of the steps above.

```python
# complex
for i in xrange(5):
   print i
```

This code is more complex than the above example. But: knowing the documentation of ´xrange´ you can understand it by a single glance. Many steps are hidden behind an easy-to-use-interface.

As processes grow bigger, the gap between complicated and complex gets wider and wider

