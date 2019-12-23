---
date: 2019-12-22 01:48:05
layout: post
title: Automatically optimise jekyll by plugins
subtitle: jekyll-minifier is a jekyll plugin for minimise not only HTML but also Javascript, JSON and CSS files. The way using it is quite simple
description: There are a lots of plugins for jekyll static site generator specially for optimising purposes such as image document and javascrpit minimization. 
image: /assets/img/uploads/2019-12-23-2.jpg
optimized_image: /assets/img/uploads/2019-12-23-2_s.jpg
category: code
tags:
  - blog
  - javascript
author: jasonma
paginate: false
---
# Optimise jekyll generator by adding plugins

There are a lots of plugins for jekyll static site generator specially for optimising purposes such as image document and javascrpit minimization. 

## jekyll-minifier
jekyll-minifier is a jekyll plugin for minimise not only HTML but also Javascript, JSON and CSS files. The way using it is quite simple, as other plugins, only neet to add the config options into the right jekyll config files and that's all.

## config for Jekflix template
First, just install the jekyll-minifier gem:

```gem install jekyll-minifier```

Then add this to your _config.yml:

```
plugins:
    - jekyll-minifier
```

But for the template I personal using, the main config file is generated from the splitted yml files. 
So you should open the ```_config.yml``` under the ```src/yml``` folder

Making the plugin section like this

```
# Plugins
plugins:
  - jekyll-paginate
  - jekyll-paginate-content
  - jekyll-minifier
 ```

Next, add the minifier plugin into ```Gemfile``` file

```gem 'jekyll-minifier'```

Also make sure run bundle command at the end

```bundle exec jekyll build```

All done, all the HTML, CSS, JS and JSON files will minify automatically after generate the new blogs or pages.





