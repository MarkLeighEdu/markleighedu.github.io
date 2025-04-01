---
layout: page
title: "Pagination Test"
permalink: /pagination-test/
paginate_path: "/pagination-test/page:num/"
---


<h1>Pagination Test</h1>
<hr>

{% assign test_posts = site.posts | where: "category", "commentary" %}
{% if test_posts.size > 0 %}
    {% for post in test_posts %}
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p>{{ post.excerpt }}</p>
        <hr>
    {% endfor %}
{% else %}
    <p>No posts found.</p>
{% endif %}

<!-- Pager -->
{% if paginator.total_pages > 1 %}
<ul>
    {% if paginator.previous_page %}
    <li><a href="{{ paginator.previous_page_path | relative_url }}">&larr; Newer Posts</a></li>
    {% endif %}
    {% if paginator.next_page %}
    <li><a href="{{ paginator.next_page_path | relative_url }}">Older Posts &rarr;</a></li>
    {% endif %}
</ul>
{% endif %}
