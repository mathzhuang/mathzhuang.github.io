---
permalink: /
title: "Hello, welcome to my homepage!"
layout: archive
author_profile: true
redirect_from:
  - /about/
  - /about.html
---
<p class="text-center" style="margin: 1em 0;">
  <img src="https://visitor-badge.laobi.icu/badge?page_id=mathzhuang.mathzhuang.github.io&left_text=visitors&left_color=%231c47f2&right_color=%2322a2ec" alt="visitors" />
</p>

I'm Ziyi Zhuang (CN name: 庄子懿), a third-year undergraduate student majoring in Software Engineering at the college of Guohao, Tongji University.

---

<section id="publications">

## Publications

{% if site.author.googlescholar %}
  <div class="wordwrap">You can also find my articles on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

{% include base_path %}

{% if site.publication_category %}
  {% for category in site.publication_category %}
    {% assign title_shown = false %}
    {% for post in site.publications reversed %}
      {% if post.category != category[0] %}{% continue %}{% endif %}
      {% unless title_shown %}
        <h3>{{ category[1].title }}</h3><hr />
        {% assign title_shown = true %}
      {% endunless %}
      {% include archive-single.html %}
    {% endfor %}
  {% endfor %}
{% else %}
  {% for post in site.publications reversed %}
    {% include archive-single.html %}
  {% endfor %}
{% endif %}

</section>

---

<section id="talks">

## Talks

{% for post in site.talks reversed %}
  {% include archive-single-talk.html %}
{% endfor %}

</section>

---

<section id="teaching">

## Teaching

{% for post in site.teaching reversed %}
  {% include archive-single.html %}
{% endfor %}

</section>

---

<section id="portfolio">

## Portfolio

{% for post in site.portfolio %}
  {% include archive-single.html %}
{% endfor %}

</section>

---

<section id="blog">

## Blog Posts

{% capture written_year %}'None'{% endcapture %}
{% for post in site.posts %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% if year != written_year %}
    <h3 id="{{ year | slugify }}">{{ year }}</h3>
    {% capture written_year %}{{ year }}{% endcapture %}
  {% endif %}
  {% include archive-single.html %}
{% endfor %}

</section>

---

<section id="cv">

## CV

Education
------
* Ph.D in Version Control Theory, GitHub University, 2018 (expected)
* M.S. in Jekyll, GitHub University, 2014
* B.S. in GitHub, GitHub University, 2012

Work experience
------
* Spring 2024: Academic Pages Collaborator
  * GitHub University
  * Duties includes: Updates and improvements to template
  * Supervisor: The Users

Skills
------
* Skill 1
* Skill 2
* Skill 3

Publications
------
<ul>{% for post in site.publications reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>

Talks
------
<ul>{% for post in site.talks reversed %}
  {% include archive-single-talk-cv.html %}
{% endfor %}</ul>

Teaching
------
<ul>{% for post in site.teaching reversed %}
  {% include archive-single-cv.html %}
{% endfor %}</ul>

</section>

---

<section id="guide">

## Guide

More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/), the [growing wiki](https://github.com/academicpages/academicpages.github.io/wiki), and you can always [ask a question on GitHub](https://github.com/academicpages/academicpages.github.io/discussions).

</section>
