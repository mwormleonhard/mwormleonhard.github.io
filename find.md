---
layout: page
title: Søg og find
permalink: /find/
---

## Søg på hele www.labnoter.dk

Viderestiller til google-søgning, med parameteren site:labnoter.dk.

<input type="text" name="find_text" id='find_text' onkeydown="if (event.keyCode == 13) document.getElementById('search_button').click();">
<button type="button" id="search_button"
onclick="location.href='http://www.google.com/search?q=site:labnoter.dk+' + document.getElementById('find_text').value;"
>
Søg!
</button>

## Emner

<!-- Al den følgende kode er fra: http://pavdmyt.com/how-to-implement-tags-at-jekyll-website/ -->
<!-- Get the tag name for every tag on the site and set them
to the `site_tags` variable. -->
{% capture site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %},{% endunless %}{% endfor %}{% endcapture %}

<!-- `tag_words` is a sorted array of the tag names. -->
{% assign tag_words = site_tags | split:',' | sort %}

<!-- List of all tags -->
<ul class="tags">
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    <li>
      <a href="#{{ this_word | cgi_escape }}" class="tag">{{ this_word }}
        <span>({{ site.tags[this_word].size }})</span>
      </a>
    </li>
  {% endunless %}{% endfor %}
</ul>

<!-- Posts by Tag -->
<div>
  {% for item in (0..site.tags.size) %}{% unless forloop.last %}
    {% capture this_word %}{{ tag_words[item] }}{% endcapture %}
    <h2 id="{{ this_word | cgi_escape }}">{{ this_word }}</h2>
    {% for post in site.tags[this_word] %}{% if post.title != null %}
      <div>
        <span style="float: left;">
          <a href="{{ post.url }}">{{ post.title }}</a>
        </span>
        <span style="float: right;">
          {{ post.date | date: "%Y-%m-%d" }}
        </span>
      </div>
      <div style="clear: both;"></div>
    {% endif %}{% endfor %}
  {% endunless %}{% endfor %}
</div>
