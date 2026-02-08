---
layout: default
title: Posts
permalink: /posts/
---

<header>
    <h1 class="page-title">Development Log</h1>
    <p style="color: var(--text-secondary); margin-top: 12px;">Structured documentation of the OS building process, organized chronologically.</p>
</header>

{% if site.posts %}
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}

{% if sorted_posts.size > 0 %}
<ul class="post-list">
{% for post in sorted_posts %}
<li class="post-item">
    <div class="post-meta">
        {{ post.date | date: "%Y-%m-%d" }}
        {% if post.tags %}
        <span class="note-tags">
            {% for tag in post.tags %}
            <span class="tag">{{ tag }}</span>
            {% endfor %}
        </span>
        {% endif %}
    </div>
    <h3 class="post-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h3>
    {% if post.excerpt %}
    <div class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</div>
    {% endif %}
</li>
{% endfor %}
</ul>
{% else %}
<p style="color: var(--text-muted); padding: 40px 0;">No posts yet. Start documenting your OS development journey!</p>
{% endif %}
{% else %}
<p style="color: var(--text-muted); padding: 40px 0;">No posts yet. Start documenting your OS development journey!</p>
{% endif %}
