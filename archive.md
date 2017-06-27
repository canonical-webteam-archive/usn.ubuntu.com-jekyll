---
layout: default
title: "archives"
permalink: /archives/index.html
---


<div class="p-strip">
  <div class="row">
    <div class="col-10">
      <h1>USN archives</h1>
    </div>
  </div>
  <div class="row">
    <div class="col-8">


    {% for cat in site.categories %}
        {% capture shortname %}{{ cat[0] | replace: '.', '-'}}{% endcapture %}

      <!-- {{ cat[0] }} -->
      <h3><a href='/archives/{{ shortname }}'>{{ cat[0] | replace: 'ubuntu-', 'Ubuntu ' | replace: '-', '.' | replace: '.lts', ' LTS' }} archives</a></h3>
      <ul>
        {% for post in cat[1] limit: 10 %}
        <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> &mdash; {{ post.date | date: "%-d %B %Y" }}</li>
        {% endfor %}
      </ul>
      {% endfor %}

    </div>
    <div class="col-4">

      <h3>Monthly archives</h3>

      <ul>
        {% for post in site.posts %}
        {% capture currentyearmonth %}{{post.date | date: "%B %Y"}}{% endcapture %}
        {% capture currentyearmonthurl %}{{post.date | date: "/archives/%Y/%m/"}}{% endcapture %}
        {% if currentyearmonth != lastyearmonth %}
        <li><a href="{{ currentyearmonthurl }}">{{ currentyearmonth }}</a></li>
        {% capture lastyearmonth %}{{currentyearmonth}}{% endcapture %}
        {% endif %}
        {% endfor %}
      </ul>

    </div>
  </div>
</div>
