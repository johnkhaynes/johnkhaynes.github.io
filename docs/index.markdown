---
layout: default
title: Home
---

<nav>
  <ul style="list-style: none; padding-left: 0; display: flex; gap: 1rem;">
    <li><a href="/">Home</a></li>
    <li><a href="/about.markdown">About</a></li>
    <li><a href="/feed.xml">RSS</a></li>
  </ul>
</nav>

# Welcome to My Blog

Thanks for stopping by! This is the homepage of my Jekyll-powered blog where I share ideas, tutorials, and updates about my work and interests.

## Latest Posts

<ul>
  {% for post in site.posts limit:5 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span style="color: gray;"> – {{ post.date | date: "%B %d, %Y" }}</span>
    </li>
  {% endfor %}
</ul>

## About This Site

This site is built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/). It's a simple and flexible way to publish content and experiment with static site generation.

Feel free to check out the [About](/about.markdown) page to learn more about me.
