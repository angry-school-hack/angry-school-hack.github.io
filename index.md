---
layout: default
---
<div class="posts">
	{% for post in site.categories.updates limit:3 %}
	<article class="post">
		<h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
		<div class="entry">
			{{ post.excerpt }}
		</div>
	</article>
	{% endfor %}
</div>

