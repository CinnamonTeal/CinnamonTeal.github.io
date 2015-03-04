# CinnamonTeal.github.io


Wacky behavior due to interplay between functions which load default layouts and styles.

note: text-decoration: param for links set to none from underlined in _sass/_base.scss (global effect)

_sass/_base.scss is loaded by a function on line 9 in _includes/head.html,  which is then loaded by _layouts/default.html, which is only relevant because the yaml front matter on index.html indicates the layout is default.

current _layouts/post.html is a copy of the clean-blog post layout, although it seems not to be loading yet. 

clean-blog resources located in CinnamonTeal.github.io/_theme_packages/startbootstrap-clean-blog-jekyll-gh-pages



How to use markdown:

This is a [link](http://example.com/).