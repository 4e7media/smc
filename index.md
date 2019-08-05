---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
{% include header.html%}
{% assign sorted = site.post | sort: 'date' | reverse %}
<div id="new-post">
    <div class="top-header">
        <h4>{{ sorted.first.date | date_to_long_string }}</h4>
        <h4>{{ sorted.first.tag | capitalize }}</h4>
        <h4>{{ sorted.post.first.author | capitalize }}</h4>
    </div>
    <h1>{{ sorted.post.first.title }}</h1>
    <div class="top-img" style="background-image:url('{{ sorted.first.img }}')"></div>
</div>
<div class="tp-border"></div>
<div class="pop-posts">
    {% for post in sorted offset:1 %}
    {% if post.pop == 1 %}
    <div class="pop-post">
        <h2>{{post.title | capitalize}}</h2>
        <div class="pop-header">
            <p>{{post.date | date_to_long_string }}</p>
            <p>{{post.tag | capitalize}}</p>
        </div>
        <div class="pop-img" style="background-image:url('{{post.img}}')"></div>
        <a href="{{post.url}}">Mehr...</a>
    </div>
    {% endif %}
    {% endfor %}
</div>
<div class="tp-border"></div>
<div class="bottom-content">
    <div class="bottom-posts">
        {% for post in sorted offset:1 %}
        {% if post.pop != 1 %}
        <div class="post">
            <h2>{{post.title}}</h2>
            <div class="bottom-header">
                <p>{{post.date | date_to_long_string }}</p>
                <p>{{post.tag}}</p>
            </div>
            <img src="{{post.img}}">
            <a href="{{post.url}}">Mehr...</a>
        </div>
        {% endif %}
        {% endfor %}
    </div>
</div>