---
layout: default
title:  "How I setup this blog"
date:   2017-09-03 14:35:46 +0700
comments: true
categories: jekyll github-pages blog
---

I already had quite a few tools installed on my laptop, like ruby, jekyll, bundler. I had these tools installed because I onced used jekyll to create a static website for [mcmi](http://www.mcmi.asia). It seems that I usually work on projects and come back to them after very long time, and forget everything about how I got things done. So now I plan to record steps I did on this blog for future reference. 

So for this blog I started following the [jekyll quick start guide](https://jekyllrb.com/docs/quickstart/). 
{% highlight console linenos %}
#Create a new jekyll site
jekyll new myblog
#switched to directory
cd myblog
#Build the site on the preview server
bundle execute jekyll serve
{% endhighlight %}

Some changes I had to make in the `_config.yml` include the following:
1. under `site settings` change `baseurl` to `/myblog` this is required for the live github repo to work properly 
2. changing `gem` to `plugins` under the `build settings`

* created a github repo by the name `myblog`
* add it as remote using the command  `git remote add origin git@github.com:beyond2013/myblog.git`
* pushed local repo to remote `git push`
* Under the settings of github repo move to section GitHub Pages
* In Source choose master branch and click Save

And thats it, [the blog](https://beyond2013.github.io/myblog/) is now live.
