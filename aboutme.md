---
layout: page
title: About me
subtitle: 
use-site-title: true
---



<div class="container">
    	<div class="row">
            <div class="col-md-6">
 <p>Welcome! My name is Cleber Vinicius Brito dos Santos. I’m currently a doctorate student at the <a href="https://https://www.ims.uerj.br"">Instituto de Medicina Social</a>. I work with <a href="https://emap.fgv.br/en/faculty/claudio-jose-struchiner"">Cláudio José Struchiner</a>, and <a href="https://publons.com/researcher/1202227/guilherme-werneck/"">Guilherme Loureiro Werneck</a>, and my current doctorate project focuses in infectious disease epidemiology, specifically we aim to evaluate and optimize vaccine trials.  </br> </br>
Previously, I did my MSc in the same institute and supervisor.  In there we estimated the causal effects of deforestation on the occurrence of Visceral Leishmaniasis in the São Paulo State (Brazil). </br> </br>
  </p>
            </div>
            <div class="col-md-6"> 
            	<br><br><br>
            	  <figure>
                <img src="img/headshot.jpeg" width = 340 height = 255 alt="Cleber">
                </figure>
		</div>
	    </div><!-- row -->
	
    </div> <!-- /container -->



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

    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <img src="{{ post.image }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags:
      {% if site.link-tags %}
      {% for tag in post.tags %}
      <a href="{{ site.baseurl }}/tag/{{ tag }}">{{ tag }}</a>
      {% endfor %}
      {% else %}
        {{ post.tags | join: ", " }}
      {% endif %}
    </div>
    {% endif %}

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
