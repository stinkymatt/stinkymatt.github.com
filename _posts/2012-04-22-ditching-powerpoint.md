---
layout: post
title: "Ditching Powerpoint"
category: tutorial 
tags: [textile, markdown, slides]
---
{% include JB/setup %}

Ditching Powerpoint for a Simpler Slide Tool
============================================

###The Problem...

Need to make slides. Hate Powerpoint. I can't be the only one. Have heard about some new-fangled HTML 5 slide thingy. Surely somebody is parsing simple bullet lists in textile or markdown into web-friendly slides, right? Google will know...

###Poking around...

[Pandoc](http://johnmacfarlane.net/pandoc/README.html) looks really interesting, but it requires a Haskell runtime, which seems like overkill just to parse some text into other text. Maybe it's the "better" solution, but simple is more important. 

The first search result is actually something called [S9](http://slideshow.rubyforge.org/). A quick perusal reveals that it's a "gem install" away, after a quick refresher on the faint memory of setting up [RVM](http://beginrescueend.com/rvm/basics/)...

###Getting S9 Running...

	rvm use default
	gem install slideshow
	
Done. Didn't really need the first line, but it doesn't hurt. Now, how to use it? Need some slide content. Some lines of Textile should work:

	h1. Slides Without Powerpoint
	
	* Slides are _really_ simple
	* Slides shouldn't require client software
	* Slides on the web are really convenient
	
	h1. The Simple Part
	
	* Textile or Markdown headers are the big titles at the top
	* Bullets are the standard bullets in Textile or Markdown (*,-)
	* That's a significant portion of all slides anywhere
	
	h1. Open Questions
	
	h2. What do subheaders do?
	* How are images and diagrams handled?
	* What about links? 
	
Now make them slides:

	slideshow slides
	
Good enough for now. Themes and more complex formatting will saved for later.