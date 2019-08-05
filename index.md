---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
{% include header.html%}
<div id="new-post">
    <div class="top-header">
        <h4>{{ site.post.first.date | date_to_long_string }}</h4>
        <h4>{{ site.post.first.tag | capitalize }}</h4>
        <h4>{{ site.post.first.author | capitalize }}</h4>
    </div>   
     <h1>{{ site.post.first.title }}</h1>
    <div class="top-img" style="background-image:url('{{ site.post.first.img }}')"></div>
</div>
<div class="tp-border"></div>
<div>
    {% for post in site.post%}
    {% if post.pop == 1 %}
    <div class="post">
        <h2>{{post.title | capitalize}}</h2>
        <p>{{post.date | date_to_long_string }}</p>
        <p>{{post.author | capitalize}}</p>
        <img src="{{post.img}}">
    </div>
    {% endif %}
    {% endfor %}
</div>
<div>
    {% for post in site.post%}
    <div class="post">
        <h2>{{post.title}}</h2>
        <p>{{post.date}}</p>
        <p>{{post.author}}</p>
        <img src="{{post.img}}">
    </div>
    {% endfor %}
</div>