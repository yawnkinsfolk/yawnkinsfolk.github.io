---
layout: page
title: Archives
---
<ul class="posts">
  {% for post in site.posts %}
    <li itemscope itemtype="https://schema.org/Blog">

      {% unless post.next %}
        <h2>{{ post.date | date: '%Y' }}</h2>
      {% else %}
        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
        {% if year != nyear %}
          <h2>{{ post.date | date: '%Y' }}</h2>
        {% endif %}
      {% endunless %}

      <a itemprop="name" href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
      <p class="post-date"><span><i class="fa fa-calendar" aria-hidden="true"></i> {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}</span></p>
    </li>

  {% endfor %}
</ul>
