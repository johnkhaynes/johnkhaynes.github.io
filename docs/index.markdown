---
layout: default
title: Home
---

# Digital Postcards from the Edge

Welcome to my little corner of the web. As we approach the coming collective transformation (aka the singularity) I felt it appropriate to record some of my thoughts and experiences. 

Here's a few of the latest:

## Latest Posts

<ul>
  {% for post in site.posts limit:10 %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span style="color: gray;"> – {{ post.date | date: "%B %d, %Y" }}</span>
    </li>
  {% endfor %}
</ul>

## About Me

I am a long-time software engineer (30+ year career in tech), recently turned full-time musician, composer, and music teacher. In college I studied Liberal Arts - not engineering - and I learned my tech skills the old-fashioned way: on the job. I have a penchant for philosophy, systems thinking, and wrestling with the 'big questions.' I'm particularly interested in how tecnhology steers us toward deeper engagement with these questions rather than seeing it as a purported answer to them. 

I never dreamed taht all of the seeming unrelated currents in my life would somehow come full circle and combine in the present, but he we are. This blog is my attempt to capture and describe some of these connections. My hope is to further discussion of profound aspects of this moment that are barely acknowledged and rarely discussed. They need to be.

## About This Site

This site is built with [Jekyll](https://jekyllrb.com/) and hosted on [GitHub Pages](https://pages.github.com/). It's a simple and flexible way to publish content and experiment with static site generation.

Check out the [About](/about.markdown) page to learn more about me.
