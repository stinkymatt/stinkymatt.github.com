---
layout: post
title: "Hello GitHub Pages"
category: tutorial 
tags: [jekyll, gh-pages, jekyll-bootstrap]
---
{% include JB/setup %}

Setting up Jekyll and a GitHub Pages site on Lion
===============================================

###Markdown

Since notes will be taken suring this process, may as well take them in a notation that can later be used as a "hello world" blog post. GitHub Pages uses Markdown, so write notes in Markdown. See: [http://github.github.com/github-flavored-markdown/](http://github.github.com/github-flavored-markdown/)

###Set up Jekyll

Will need to push some content to see site once it's configured. Could just blindly follow instructions for jekyll and hope it works, or push dumb index.html file, but that's boring. So, need Jekyll running on Lion. [This site](http://brandonbohling.com/2011/08/27/Installing-Jekyll-on-Mac/) has good instructions on doing that, but isn't ideal/up-to-date. First off, don't want to install the _huge_ XCode suite just to format some text. Found a [StackOverflow](http://stackoverflow.com/a/7033507/72676) answer that points to a nice precompiled package of compiler tools that is needed in order to install a new version of Ruby, so the GitHub version of Jekyll can be matched. Download the package from this Git repo: [https://github.com/kennethreitz/osx-gcc-installer](https://github.com/kennethreitz/osx-gcc-installer)

Install the Lion version as usual...

Then follow the guidance given by initial blog post to install RVM, though the process is slightly changed from what is published on that site. These instructions complete the process of getting Jekyll configured:

	bash -s stable < <(curl -s https://raw.github.com/wayneeseguin/rvm/master/binscripts/rvm-installer)
	source ~/.bash_profile
	rvm install 1.9.2 #Or later version if applicable
	rvm alias create default 1.9.2
	rvm use default
	gem install jekyll
	gem install jekyll-tags

Great, Now what?

###Set up repo

Create repo on GitHub: stinkymatt.github.com
Then STOP!... <del>Follow instructions to init repo and make initial push.
Note that even after 10 minutes, the site doesn't show up if there is just a README in "master".</del> Don't follow those instructions... 

Following the basic getting started instructions will result in way too much work to get to an unprofessionally bare-bones site. (five hours of googling/trial&error I won't soon be getting back...) Instead, use [jekyll-bootstrap](http://jekyllbootstrap.com/), fill out form on that page, to get personalized instructions to set up repo, but pushing to github is probably premature at this point. Code used here:

	git clone https://github.com/plusjade/jekyll-bootstrap.git stinkymatt.github.com
	cd stinkymatt.github.com
	git remote set-url origin git@github.com:stinkymatt/stinkymatt.github.com.git


###Use Jekyll

While in root directory of site (~/Documents/stinkymatt.github.com in this case) run ```jekyll --server --pygments --safe```, then fire up [http://localhost:4000/](http://localhost:4000/) in browser to preview.

Very nice, but has default content what needs purgin'. And a non-defualt theme would be nice. Also need to fix defaults.

* Edit \_config.yml using common sense to customize.
* ```rake post title="Hello GitHub Pages"```
* Add content to the file in \_posts that the rake task just created.

Things are pretty close now, but the landing page needs customization. For that, just edit index.md to replace the default content. Then just push the repo back up to github.



