---
layout: post
title:  "How to listen for changes to the Title element?"
date:   2024-03-14 18:22:45 +0700
categories: javascript
---
In Javascript, is there a technique to listen for changes to the title element?

{% highlight js %}
// select the target node
var target = document.querySelector('title');

// create an observer instance
var observer = new MutationObserver(function(mutations) {
    // We need only first event and only new value of the title
    console.trace(mutations[0].target.nodeValue);
});

// configuration of the observer:
var config = { subtree: true, characterData: true, childList: true };

// pass in the target node, as well as the observer options
observer.observe(target, config);
{% endhighlight %}
