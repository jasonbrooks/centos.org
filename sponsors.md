---
title:      "CentOS Sponsors"
markdown:   basic
is_dynamic: true
is_hidden: false
layout: default
---

<div class="row">
  <div class="jumbotron col-md-12">
    <h1>Sponsors</h1>
    <p>If you are interested in becoming a CentOS sponsor, you can contact the us at <a href="mailto:donate@centos.org">donate@centos.org</a>.</p>
  </div>
</div>


<div class="row">
  {% for sponsor in site.data.sponsors %}
    <div class="col-sm-6 col-md-4" >
      <div class="thumbnail">
        <img class="rounded" src="{{ sponsor.img }}">
          <div class="caption">
            <h3>{{ sponsor.name }} </h3>
              <p> <a href="{{ sponsor.url }}" rel="nofollow">{{ sponsor.url }}</a></p>
          </div>
        </div>
      </div>
  {% endfor %}
</div>
