---
layout: post
title: "Custom SASS Directory With Sinatra"
date: 2013-07-10 03:34
comments: true
categories: ruby sinatra slim
---

A few days ago I started using [sass](http://sass-lang.com) on my [sinatra](http://sinatrarb.com) web project. Instead of variable, mixin features, it's also the best solution to save my time in developing on boring css coding.
<!-- more -->
To use this stuff, i should ensure that i require this gem ant top of my application file, and then i have to create a route handler for it. Simple, isn't it? 


```ruby main.rb
require 'sass'

get('/styles.css'){ scss :styles }
```
With all of this simplicity, i still dont satisfied yet with the default folder, each time i have to put the sass on views directory, what a mess!

Finally, i find a solution to make my own custom directiory, i just need to set up the sass directory on the main app file, in this case i wanted to put the sass file on scss directory, and it will be below :

```ruby main.rb
set :views, :scss => 'views/sass/', :default => 'views'

 helpers do
   def find_template(views, name, engine, &block)
     _, folder = views.detect { |k,v| engine == Tilt[k] }
     folder ||= views[:default]
     super(folder, name, engine, &block)
   end
 end


get '/css/styles.css' do
	scss :styles
end
```

with tree structure 

```bash
├── main.rb
└── views
    ├── main.slim
    └── sass
        └── styles.scss

2 directories, 3 files

```
when i run it, everything is doing pretty well, and i love it so much

If you want to see the result file, just feel free to open this [link](https://github.com/muslih/sinatra-custom-sass-directory)

