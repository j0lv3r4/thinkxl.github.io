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
