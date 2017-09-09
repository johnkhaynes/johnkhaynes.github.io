---
layout: default
title:  "Blogging with Jekyll"
date:   2017-09-08 10:28:02 -0700
categories: blog update
---

[Jekyll](https://jekyllrb.com/docs/home/) is static web site generator built in Ruby. From the web site:

> Jekyll is a simple, blog-aware, static site generator. It takes a template
directory containing raw text files in various formats, runs it through a
converter (like Markdown) and our Liquid renderer, and spits out a complete,
ready-to-publish static website suitable for serving with your favorite web server.


## Jekyll & Markdown

When you think about it, a static site generator is a lot like a compiler. Thus using standard software development tools with Jekyll seems like a natural fit. Combine this with the ease and power of markdown, and you instantly have a super-low-friction blogging platform. To update the blog, all you have to do is write a new post in markdown, commit the change to the remote repository, and the blog site is automatically updated.

*Way cool.*

<p align="center">
<img src="https://talk.jekyllrb.com/uploads/jekyllrb/original/1X/4f9bd5334246d33651e846aed812280fbff586ba.png" width="200"/>
</p>

## Site Theme Configuration

Here are few notes so that later I can remember the steps I took to configure the site. Once I understood that static nature of the site generator and how everything worked configuring everything made a lot more sense.

There are only a handful of Jekyll themes supported out of the box on the Github site. I quickly realized that only the default `minima` theme had any support for blogging. After a quick google search I discovered a variant of the standard Cayman theme called [Cayman Blog Theme](https://lorepirri.github.io/cayman-blog/).

The [README](https://github.com/lorepirri/cayman-blog/blob/master/README.md) file describes a couple of different ways to configure the theme for use on the Github Pages site. I opted for the first method.  Here are a few important notes from the `README` file.

## Hosting with GitHub Pages

If you’re *hosting your blog with GitHub Pages* you’ll have to consider this:

:warning: As stated in the official [Jekyll documentation](https://jekyllrb.com/docs/themes/#installing-a-theme):

> If you’re publishing your Jekyll site on [GitHub Pages](https://pages.github.com/), note that GitHub Pages supports only some gem-based themes. See [Supported Themes](https://pages.github.com/themes/) in GitHub’s documentation to see which themes are supported.

Therefore, this theme, as well as many others, can not be installed in the same way as the ones officially supported by GitHub Pages (e.g. Cayman, Minima), a bit more effort has to be put on.

The easiest way I found to install _Cayman Blog Theme_, is [installing the theme gem](gem-install), and then [converting the gem-based theme to regular theme](https://jekyllrb.com/docs/themes/#converting-gem-based-themes-to-regular-themes).

Alternatively, for new projects, one could fork the whole theme, and keep only the interesting files.


### Gem Install

This method is preferred for existing _Jekyll blogs_, as well as newly created ones. Notice that the files `index.md`, `about.md`, `contact.md` will be overwritten (only `index.md` is really needed, the other two are just placeholders).

1. Install the theme gem: ` $ gem install jekyll-theme-cayman-blog`
3. Run `$ gem env gemdir` to know where the gem was installed
4. Open the folder shown in the output
5. Open the folder `gems`
5. Open the theme folder (e.g. `jekyll-theme-cayman-blog-0.0.5`)
6. Copy all the files into your newly created or existing blog folder    
7. Leave empty `theme` your site's `_config.yml`:

    ```yml
    theme:
    ```
6. Modify `_config.yml`, `about.md`, `contact.md` for your project

## Running Locally

In order to set everything up on my Mac locally, I created a new test blog:

```bash
# create new test blog
~ $ jekyll new testblog

# cd to new blog directory
~ $ cd testblog

# run the test server
~testblog $ bundle exec jekyll serve

# browse to localhost:4000 to test

```

Once I determined that everything was running correctly I then copied the contents of the theme gem to the new blog. I edited the `_config.yml` file to remove the default theme, and I then restarted the server to confirm that everything was running with the new theme.

Once I got the test server working, I copied the contents of the test server over to my working directory for my remote git repo. In order to 'deploy' the new web site, all I had to do was commit my changes and push everything up to the remote git repository on the Github site. At that point my new site was live and everything was up and running.
