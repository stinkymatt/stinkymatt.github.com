---
layout: page
title: StinkyMatt's GitHub Pages
---
{% include JB/setup %}

##Hello

Hopefully this is useful. The site is incomplete in the spirit of [Worse is Better](http://en.wikipedia.org/wiki/Worse_is_better) so that it can be published before it's really complete. Ideally, I'd like to have this landing page display an excerpt of the latest blog post, but that bit of Jekyll-foo eludes me... for now.

Update: I'm trapped with this solitary post because my GitHub Pages aren't regenerating when I push. Something to do with the following:
	No submodule mapping found in .gitmodules for path '_theme_packages/the-program'

##Posts
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


