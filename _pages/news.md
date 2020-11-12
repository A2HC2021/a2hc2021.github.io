---
title: News
permalink: /news/
classes: single
author: A2hc2021
---

{% assign timeframe = 604800 %}
{% assign maxposts = 10 %}
{% assign date_format = site.minima.date_format | default: "%m/%d" %}

<ul class="post-list text-muted list-unstyled">
{% for post in site.posts %}
  {% assign post_in_seconds = post.last_modified_at | date: "%s" | plus: 0 %}
  {% assign recent_posts = "now" | date: "%s" | minus: timeframe %}
  {% assign post_updated = post.last_modified_at | date: date_format %}
  {% capture post_date %}<small>{{ post.date | date: date_format }}</small>{% endcapture %}

  {% if post_in_seconds > recent_posts %}
  {% capture label_new %}<span class="label label-primary">new</span>{% endcapture %}
    {% if post.last_modified_at > post.date %}
      {% assign label_new = '' %}{% comment %}Clear NEW if modified{% endcomment %}
      {% capture label_updated %}<span class="label label-info">Updated <span class="badge">{{ post_updated }}</span></span>{% endcapture %}
    {% endif %}
  {% endif %}
  <li>
    <h4>{{ post_date }}
      <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}</a> {{ label_new }}{{ label_updated }}
      </h4>
       <small><em> {{ post.excerpt }} </em></small>
  </li>
  {% assign post_date = '' %}
  {% assign label_updated = '' %}
{% endfor %}
</ul>
