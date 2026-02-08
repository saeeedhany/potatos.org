---
layout: default
---
<div class="roadmap-banner">
    <div class="roadmap-icon">🗺️</div>
    <div class="roadmap-content">
        <h2>OS Development Roadmap</h2>
        <p>Track the complete development journey from bootloader to userspace</p>
        <a href="{{ '/roadmap' | relative_url }}" class="roadmap-btn">View Full Roadmap →</a>
    </div>
</div>
<header>
    <h1 class="page-title">About This Project</h1>
</header>
<div class="about-section">
    <p>
        This is a documentation site for <strong>potatOS</strong>, a hobby operating system built from scratch as a learning project.
        The primary goal is to understand how operating systems actually work by implementing core components manually,
        rather than relying on existing abstractions.
    </p>
</div>
<div class="philosophy">
    <h2>Philosophy</h2>
    <p>
        potatOS exists as an exploration of operating system internals, from early boot stages to kernel subsystems.
        It is not intended to be practical, stable, or production-ready.
        Instead, it serves as a personal environment for experimentation, learning, and understanding mistakes.
    </p>
    <h3>Principles</h3>
    <p>
        The project focuses on simplicity, clarity, and learning through implementation.
        Every component is written with the intent to understand why it exists, how it works internally,
        and what trade-offs it introduces — even if that means reinventing things inefficiently or imperfectly.
    </p>
</div>
<h2>Recent Updates</h2>
{% assign sorted_posts = site.posts | sort: 'date' | reverse %}
<ul class="post-list">
    {% for post in sorted_posts limit:5 %}
    <li class="post-item">
        <h3 class="post-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        </h3>
        <div class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</div>
        {% if post.excerpt %}
        <div class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 30 }}</div>
        {% endif %}
    </li>
    {% endfor %}
</ul>

{% if site.posts.size > 5 %}
<div class="see-more-container">
    <a href="{{ '/posts' | relative_url }}" class="see-more-btn">See More Posts →</a>
</div>
{% endif %}

