---
layout: default
title: Learning Modules
---

# Learning Modules

Welcome to our comprehensive collection of learning modules designed to build your skills in data analytics and research. Choose from five specialized tracks to advance your expertise.

<div class="tracks-grid">
{% for track in site.data.modules.tracks %}
    <div class="track-card" style="border-left: 4px solid {{ track.color }}">
        <h2>{{ track.name }}</h2>
        <p>{{ track.description }}</p>
        
        <div class="modules-list">
            {% for module in track.modules %}
                <div class="module-item">
                    <h3>{{ module.title }}</h3>
                    <p>{{ module.description }}</p>
                    <div class="module-meta">
                        <span class="duration">{{ module.duration }}</span>
                        <span class="level level-{{ module.level | downcase }}">{{ module.level }}</span>
                    </div>
                </div>
            {% endfor %}
        </div>
    </div>
{% endfor %}
</div>

## Getting Started

1. **Choose Your Track**: Select the learning track that best fits your current skill level and goals
2. **Follow the Sequence**: Modules are designed to build upon each other
3. **Practice Regularly**: Apply what you learn through hands-on exercises
4. **Join the Community**: Connect with other learners and share your progress

<div class="cta-section">
    <a href="https://asmuie-analytics.github.io/" class="btn btn-primary">Visit Main Site</a>
    <a href="https://asmuie-analytics.github.io/projects/" class="btn btn-secondary">View Projects</a>
</div>
