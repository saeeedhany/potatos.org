---
layout: default
title: Notes
permalink: /notes/
---

<header>
    <h1 class="page-title">Development Notes</h1>
    <p style="color: var(--text-secondary); margin-top: 12px;">Random thoughts, learnings, and research notes from the OS development journey.</p>
</header>

{% if site.notes %}
{% assign sorted_notes = site.notes | sort: 'date' | reverse %}

{% if sorted_notes.size > 0 %}
<ul class="post-list">
{% for note in sorted_notes %}
<li class="post-item">
    <div class="post-meta">
        {{ note.date | date: "%Y-%m-%d" }}
        {% if note.tags %}
        <span class="note-tags">
            {% for tag in note.tags %}
            <span class="tag">{{ tag }}</span>
            {% endfor %}
        </span>
        {% endif %}
    </div>
    <h3 class="post-title">
        <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
    </h3>
    {% if note.excerpt %}
    <div class="post-excerpt">{{ note.excerpt | strip_html | truncatewords: 30 }}</div>
    {% endif %}
</li>
{% endfor %}
</ul>
{% else %}
<p style="color: var(--text-muted); padding: 40px 0;">No notes yet. Start documenting your learnings!</p>
{% endif %}
{% else %}
<p style="color: var(--text-muted); padding: 40px 0;">No notes yet. Start documenting your learnings!</p>
{% endif %}
