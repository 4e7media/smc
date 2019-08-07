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
        <h4>{{ sorted.first.author | capitalize }}</h4>
    </div>
    <h1>{{ sorted.first.title }}</h1>
    <img class="top-img" src="{{ sorted.first.img }}">
</div>
<div class="tp-border"></div>
<div class="pop-posts">
    {% for post in sorted offset:1 limit:2 %}
    <div class="pop-post">
        <h2>{{post.title | capitalize}}</h2>
        <div class="pop-header">
            <p>{{post.date | date_to_long_string }}</p>
            <p>{{post.tag }}</p>
        </div>
        <img class="pop-img" src="{{post.img}}">
        <a href="{{post.url}}">Mehr...</a>
    </div>
    {% endfor %}
</div>
<div class="tp-border"></div>
<div class="bottom-content">
    <div class="bottom-posts">
        {% for post in sorted offset:4 %}
        <div class="post">
            <h2>{{post.title}}</h2>
            <div class="bottom-header">
                <p>{{post.date | date_to_long_string }}</p>
                <p>{{post.tag}}</p>
            </div>
            <img src="{{post.img}}">
            <a href="{{post.url}}">Mehr...</a>
        </div>
        {% endfor %}
    </div>
    <div class="side-bar">
        <div class="fb-cont">
            <h3>FACEBOOK</h3>
            <a href="https://www.facebook.com/smClubAustria/"><img src="/img/fb.png"></a>
        </div>
        <div class="side-posts">
            <h3>MOST POPULAR ON SMCA</h3>
            {% for post in sorted offset:1 limit:2 %}
            {% if post.pop == 1 %}
            <div class="side-post">
                <a href="{{post.url}}"><div class="side-img" style="background-image:url('{{post.img}}')"></div></a>
                <a href="{{post.url}}"><h2>{{post.title | capitalize}}</h2></a>
                <div class="side-header">
                    <p>{{post.date | date_to_long_string }}</p>
                    <p>{{ post.tag }}</p>
                </div>
            </div>
            {% endif %}
            {% endfor %}
        </div>
    </div>
</div>