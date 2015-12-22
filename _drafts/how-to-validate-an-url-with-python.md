---
layout: post
title: How to Validate an URL with Python
tag:
- Python
- Snippets
author: Juan Olvera
twitter: thinkxl
---

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.


{% highlight python %}
def is_url(url):
    parsed_url = urlparse.urlparse(url)
    return bool(parsed_url.scheme)
{% endhighlight %}
