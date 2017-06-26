---
layout: default
title: "Ubuntu security notices"
---

<div class="p-strip">
  <div class="row">
    <div class="col-10">
      <p>These are the Ubuntu security notices that affect the current supported releases of Ubuntu. These notices are also posted to the <a href="https://lists.ubuntu.com/mailman/listinfo/ubuntu-security-announce">ubuntu-security-announce</a> mailing list (<a href="https://lists.ubuntu.com/archives/ubuntu-security-announce/">list archive</a>). To report a security vulnerability in an Ubuntu package, please <a href="https://wiki.ubuntu.com/SecurityTeam/FAQ#Contact">contact</a> the Ubuntu Security Team. You may also be interested in learning about <a href="https://wiki.ubuntu.com/SecurityTeam/Policies">Ubuntu security policies</a>. For more details on a specific CVE or source package, please see the <a href="http://people.canonical.com/~ubuntu-security/cve/">Ubuntu CVE Tracker</a>.</p>
      <p>You can also view the latest notices by subscribing to the <a href="/usn/rss.xml">RSS <img src="https://assets.ubuntu.com/v1/f727d471-feed.png" alt=""></a> or the <a href="/usn/atom.xml">Atom <img src="https://assets.ubuntu.com/v1/f727d471-feed.png" alt=""></a> feeds.</p>
    </div>
  </div>
</div>

<div class="p-strip">
  <div class="row">
    <div class="col-10">
    <!-- eight main stories -->
    {% for post in site.posts limit: 8 %}
        <h2><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h2>

        {{ post.excerpt }}

        <p>{{ post.date | date: "%-d %B %Y" }} | {{ post.categories | join: ', ' }}</p>
    {% endfor %}
    <!-- /end eight main stories -->
    </div>
  </div>
</div>
