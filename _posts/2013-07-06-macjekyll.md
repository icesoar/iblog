---
layout: post
title: "Mac下安装Jekyll"
description: ""
category: [tools]
tags: [mac,jekyll,install]
---
{% include JB/setup %}

###Install Jekyll on a Mac

Copied from:  [https://github.com/tillnagel/unfolding/wiki/Install-Jekyll-on-a-Mac](https://github.com/tillnagel/unfolding/wiki/Install-Jekyll-on-a-Mac)

1. On OSX you need to 
	* Install XCode for Mac
	* Execute XCode (to install it fully)
	* Install Command Line Tools in XCode. Execute XCode again, go to Preferences > Downloads, and Install "Command Line Tools"
	* Update RubyGems with
	  `sudo gem update --system`
2. Install Jekyll on your local system
	* `sudo gem install jekyll` (See also https://github.com/mojombo/jekyll/wiki/Install )
	
3. Switch to branch "gh-pages"

4. Edit or create pages
	* e.g. /doc/usage/my_new_tutorial.md
	* See other tutorials and the Markdown syntax for a how-to
	http://daringfireball.net/projects/markdown/syntax

5. Optional: Run Jekyll on your local machine
	`jekyll --server`

Which creates the pages, and runs a local server on http://localhost:4000/
