---
layout: page
title: پروژه‌های من 
permalink: projects
---

<div>
<h2 class="font-bold text-sm">پروژه‌های من چیست؟</h2>
<p>در اینجا برخی از پروژه‌ها و خروجی‌های کارهایی که انجام داده ام را قرار می‌دهم.</p>
  {% for project in site.projects %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ project.url }}">{{ project.title}}</a></h3>
    <div class="text-sm text-gray-400" id="date@{{project.date}}"></div>
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


