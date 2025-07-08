---
layout: default
title: Learning Modules
---

<div class="page-header">
    <h1>Learning Modules</h1>
    <p>Comprehensive learning modules designed to build your skills in data analytics and research. Choose from five specialized tracks to advance your expertise.</p>
</div>

<div class="tracks-grid">
{% for track in site.data.modules.tracks %}
    <div class="track-card" data-color="{% case track.name %}{% when 'Academic Research' %}green{% when 'Basic Programming' %}blue{% when 'Data Management' %}orange{% when 'Data Visualization' %}purple{% when 'Statistical Analysis' %}red{% endcase %}">
        <h2>{{ track.name }}</h2>
        <p>{{ track.description }}</p>
        
        <div class="modules-list">
            {% for module in track.modules %}
                <div class="module-item">
                    <div class="module-header">
                        <h3><a href="{{ module.url | default: ('/' | append: track.id | append: '/' | append: module.slug | append: '/') | relative_url }}">{{ module.title }}</a></h3>
                        <p>{{ module.description }}</p>
                        
                        <div class="module-meta">
                            <span class="meta-badge duration">{{ module.duration }}</span>
                            <span class="meta-badge level-{{ module.level | downcase }}">{{ module.level }}</span>
                        </div>
                    </div>
                    
                    <div class="module-actions">
                        <a href="{{ module.url | default: ('/' | append: track.id | append: '/' | append: module.slug | append: '/') | relative_url }}" class="module-btn btn-primary">
                            Start Module →
                        </a>
                        
                        {% if module.external_url %}
                            <a href="{{ module.external_url }}" target="_blank" class="module-btn btn-success">
                                External Course ↗
                            </a>
                        {% endif %}
                        
                        {% if module.github_repo %}
                            <a href="{{ module.github_repo }}" target="_blank" class="module-btn btn-secondary">
                                GitHub ↗
                            </a>
                        {% endif %}
                    </div>
                    
                    {% if module.materials %}
                        <div class="module-materials">
                            <h4>Resources</h4>
                            <ul>
                                {% for material in module.materials %}
                                    <li><a href="{{ material.url }}" target="_blank">{{ material.title }}</a></li>
                                {% endfor %}
                            </ul>
                        </div>
                    {% endif %}
                </div>
            {% endfor %}
        </div>
    </div>
{% endfor %}
</div>

<div class="cta-section">
    <h2>Ready to Start Learning?</h2>
    <p>Join our community of learners and advance your data analytics skills</p>
    <a href="https://asmuie-analytics.github.io/" class="btn">Visit Main Site</a>
    <a href="https://asmuie-analytics.github.io/projects/" class="btn">View Projects</a>
</div>
