---
layout: page
---

Blog posts primarily concerning physics education, my ongoing projects, as well as hobbies such as game design.

{% assign categories = site.categories | sort %}
{% for category in categories %}
<h3>Topic: {{ category | first }}</h3>
<p>{% for posts in category %} {% for post in posts %}
      <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>{% if forloop.last == false %},&nbsp;&nbsp;{% endif %}
  {% endfor %} {% endfor %}  </p>
{% endfor %}
