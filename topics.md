---
title: Topics
layout: page
---
<div class="container">
    <h2 class="title">
        This page shows all GitHub repos, grouped by the topics assigned to them.
    </h2>
</div>    

{% assign sorted_topics = site.data.all_topics | sort %}
<div id='repo-topics'>
{% for topic in sorted_topics %}
    <div>
        <a href="#topic-{{ topic[0] }}"><h2 id="topic-{{ topic[0] }}">&#35;{{ topic[0] }}</h2></a>

        {% assign repos = topic[1] %}
        <div class="columns is-multiline">
            {% for repo_data in repos %}
                {% assign repo = repo_data[1] %}
                <div class="column is-3-widescreen is-4-desktop is-6-tablet is-8-mobile">
                    {% include repo-card.html %}
                </div>
            {% endfor -%}
        </div>

        <br>
    </div>
{% endfor %}
</div>
