---
layout: post
title: "Sinatra Reloader"
date: 2013-06-12 18:30
comments: true
categories: ruby sinatra reloader contrib 
---

I started to learn [sinatra](http://sinatrarb.com) since three months ago, exactly when I started to learn both [sass](http://sass-lang.com/) and [compass](http://compass-style.org/), the funny and useful css preprocessor I ever met even though I never used less at all, I think sass had enough for me :D
<!-- more -->
Even [sinatra](http://sinatrarb.com) is a simple and elegant for me, i still found a bored thing, ya, when i've made a change to my code, i have to go back to the terminal and hold down `Ctrl+C`, i have to restart every change on my file, and it could become tiresome for me. It doesn't mean i hate sinatra :D

Finally, i found the solution for this bored thing, it's was worth using sinatra reloader, i just simply type on ma `darkfury`

```
sudo gem instal sinatra-contrib
```

Then i just simply add new live below `require 'sinatra'` line, 
```
require 'sinatra'
require 'sinatra/reloader' if development?
```
Now, i just could say good bye `Ctrl+C` i do not use you anymore, all i need just only simple reload my page for my existing code. 


