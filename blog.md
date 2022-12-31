---
layout: page
title: نوشته‌ها
permalink: blog
---

<div>
  {% for post in site.posts %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ post.url }}">{{ post.title}}</a></h3>
    <div class="text-sm text-gray-400" id="date@{{post.date}}"></div>
    </div>
{% endfor %}
</div>
<script>
    document.addEventListener("DOMContentLoaded", function () {
        var dates = document.querySelectorAll('[id^="date@"]')
        let i =0
        while (i < dates.length) {
            let element = document.getElementById(dates[i].id)
            let postDate = dates[i].id.split('@')[1]
            moment.loadPersian(true)
            element.innerText = moment(postDate, 'YYYY-M-D HH:mm:ss TZD').format('ddd jD jMMMM jYYYY')
            i++
        }
    });
</script>


