---
layout: post
title: Uniquify lists in python 
tag:
- Python
- Snippets
author: Juan Olvera
twitter: thinkxl
---

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. 

{% highlight python %}
def uniquify(list_one, list_two):
	return list(set(list_one) - set(list_two))
{% endhighlight %}

### Further reading:
- [Uniquify all pairs in a python list](http://stackoverflow.com/questions/12917686/uniquify-all-pairs-in-a-python-list)
- [Uniquifying a list of lists in python](http://stackoverflow.com/questions/21442117/uniquifying-a-list-of-lists-in-python)
- [Python removing duplicates in lists](http://stackoverflow.com/questions/7961363/python-removing-duplicates-in-lists)
