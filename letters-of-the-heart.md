---
layout: default
title: Letters of the Heart
permalink: /letters-of-the-heart/
tags:
  - Our Agents
---
{% for post in site.tags["Letters of the Heart"] %}
  <div class="row content-container">
    <div class="col-sm-12">
      <h2 class="post-overview-title"><a class="post-link" href="{{ post.url }}">{{ post.title | truncate: 70 }}</a> - {{ post.date | date: "%b %-d, %Y" }}</h2>
      <hr />
    </div>

    <ul class="post-list">
      <li>
      <div class="col-lg-6 post-image-container">
        <div class="post-excerpts">
          <a href="{{post.url}}">
            {% if post.use_youtube_image == true %}
            <img src="https://img.youtube.com/vi/{{post.youtube_code | remove: 'https://youtu.be/' | remove: 'https://www.youtube.com/watch?v='}}/maxresdefault.jpg" alt="{{post.title}}" class="post-image" />
            {% else %}
            <img src="{{post.youtube_alternate_image}}" alt="{{post.title}}" class="post-image"/>
            {% endif %}
          </a>
        </div>
      </div>
      <div class="col-lg-6">
        {{ post.excerpt | strip_html | prepend: '<p class="excerpt">' | truncate: 160 }}</p>
          <p class="readlink"><a href="{{post.url}}" class="readmore">Read More</a></p></div>
    </li>
  </ul>
</div>
{% endfor %}
