---
layout: page
title: Hey, I'm Cody
subtitle: Undergraduate engineering student at Duke University

css: "/css/index.css"
meta-title: "Cody Li"
meta-description: "More than you would ever want to know about me...and more!"
bigimg:
  - "/img/avatar-icon.png" : "Test"


<!-- <div style="text-align:center">
  <strong>Quick Links:</strong> <a href="http://derekogle.com/fishR/">fishR website</a> | <a href="http://derekogle.com/IFAR/">Introductory Fisheries Analyses with R</a>
</div>
 -->

---
<div class="posts-list">
  {% for post in paginator.posts %}
  <article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
	  <h2 class="post-title">{{ post.title }}</h2>
	
	  {% if post.subtitle %}
	  <h3 class="post-subtitle">
	    {{ post.subtitle }}
	  </h3>
	  {% endif %}  
    </a>

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>
  
    <div class="post-entry">
      {{ post.content | truncatewords: 50 | strip_html | xml_escape}}
	  <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
    </div>
  
   </article>
  {% endfor %}
</div>

{% if paginator.total_pages > 1 %}
<ul class="pager main-pager">
  {% if paginator.previous_page %}
  <li class="previous">
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li class="next">
    <a href="{{ paginator.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
  </li>
  {% endif %}
</ul>
{% endif %}
