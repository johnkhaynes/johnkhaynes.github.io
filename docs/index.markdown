---
layout: default
title: Home
---

<div class="home-layout">
  <div class="main-content">
    <h1>Digital Postcards from the Edge</h1>

    <p>Welcome to my little corner of the web. As we approach the coming collective transformation (aka The Singularity), I feel compelled to record some of my thoughts, feelings, and observations as all of this unfolds.</p>

    <p>Here's a few of the latest:</p>

    <h2>Latest Posts</h2>

    <ul>
      {% for post in site.posts limit:10 %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a> - {{ post.date | date: "%B %d, %Y" }}
        </li>
      {% endfor %}
    </ul>

    <h2>About Me</h2>

    <p>I am a long-time software engineer (30+ year career in tech), recently turned full-time musician, composer, and music teacher. In college I studied Liberal Arts - not engineering - and I learned my tech skills the old-fashioned way: on the job. I have a penchant for philosophy, systems thinking, seeing the big picture, and wrestling with the 'big questions.' I'm particularly interested in how tecnhology steers us toward deeper engagement with these questions rather than seeing it as a purported answer to them.</p>

    <p>I never dreamed that all of the seeming unrelated currents in my life would somehow come full circle and combine this way in the present moment, but here we are. This blog is my attempt to capture and describe some of these connections and insights as they unfold, and as I do my best to grapple with and make sense of them. My hope is to spark both curiousity and conversation as we approach this inflection point. This historical moment presents profound questions to all of us as we live through a period of radical and unprecendented change. Many of these questions are barely acknowledged and little discussed, and engaging with them in a deep way seems to be even rarer. In our headlong rush into the future, I feel strongly that we need to take the time to reflect and allow ourselves to be transformed by these questions, just as humans have done throughout known history.</p>

    <h2>About This Site</h2>

    <p>This site is built with <a href="https://jekyllrb.com/">Jekyll</a> and hosted on <a href="https://pages.github.com/">GitHub Pages</a>. It's a simple and flexible way to publish content and experiment with static site generation.</p>

    <p>Check out the <a href="/about">About</a> page to learn more about me.</p>
  </div>

  <div class="sidebar">
    <h3>Categories</h3>
    <div class="tag-cloud">
      {% assign categories = site.categories | sort %}
      {% for category in categories %}
        {% assign post_count = category[1] | size %}
        <a href="{{ '/category/' | append: category[0] | relative_url }}" class="tag tag-{{ post_count }}">
          {{ category[0] }} ({{ post_count }})
        </a>
      {% endfor %}
    </div>
  </div>
</div>