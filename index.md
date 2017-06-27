---
layout: default
title: "Ubuntu security notices"
---

<section class="p-strip is-deep u-image-position">
  <div class="row">
    <div class="col-8">
      <p>These are the Ubuntu security notices that affect the current supported releases of Ubuntu. These notices are also posted to the <a href="https://lists.ubuntu.com/mailman/listinfo/ubuntu-security-announce">ubuntu-security-announce</a> mailing list (<a href="https://lists.ubuntu.com/archives/ubuntu-security-announce/">list archive</a>). To report a security vulnerability in an Ubuntu package, please <a href="https://wiki.ubuntu.com/SecurityTeam/FAQ#Contact">contact</a> the Ubuntu Security Team. You may also be interested in learning about <a href="https://wiki.ubuntu.com/SecurityTeam/Policies">Ubuntu security policies</a>. For more details on a specific CVE or source package, please see the <a href="http://people.canonical.com/~ubuntu-security/cve/">Ubuntu CVE Tracker</a>.</p>
      <p>You can also view the latest notices by subscribing to the <a href="/usn/rss.xml">RSS <img src="https://assets.ubuntu.com/v1/f727d471-feed.png" alt=""></a> or the <a href="/usn/atom.xml">Atom <img src="https://assets.ubuntu.com/v1/f727d471-feed.png" alt=""></a> feeds.</p>
    </div>
    <div class="col-4">
      <div style="overflow: hidden;">
        <img class="u-image-position--top u-hidden--small" src="{{ site.assets_path }}99d49a7d-padlock-chain.png" alt="" style="top: -65%; z-index: -1;" />
      </div>
    </div>
  </div>
</section>

<section class="p-strip--light">
  <div class="row">
    <div class="col-8">
      <h2>Latest notices</h2>
      <!-- eight main stories -->
      {% for post in site.posts limit: 8 %}
      <h3 class="p-heading--four"><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h3>
      {{ post.excerpt | markdownify }}
      <p>{{ post.date | date: "%-d %B %Y" }} | {{ post.categories | join: ', ' }}</p>
      {% endfor %}
      <!-- /end eight main stories -->
    </div>
    <div class="col-4 prefix-1">
      <h2 class="p-heading--three">By release</h2>
      <ul class="p-list">
        {% for cat in site.categories reversed %}
        {% capture shortname %}{{ cat[0] | replace: '.', '-'}}{% endcapture %}
        <li class="p-list__item is-ticked"><a href='/archives/{{ shortname }}'>{{ cat[0] | replace: 'ubuntu-', 'Ubuntu ' | replace: '-', '.' | replace: '.lts', ' LTS' }}</a></li>
        {% endfor %}
      </ul>
    </div>
  </div>
</section>
