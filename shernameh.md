---
layout: page
title: شرنامه
permalink: shernameh
---

<div>
<h2 class="font-bold text-sm">شرنامه چیست؟</h2>
<p>شرنامه یک توییتر شخصی است که چیزهای موقتی، درد و دل، اعصاب خرابی و شر و ور‌های خودم را اینجا می‌نویسم.</p>
  {% for sher in site.shers %}
    <div class="py-1">
      <h3><a href="{{site.baseurl}}{{ sher.url }}">{{ sher.title}}</a></h3>
    <div class="text-sm text-gray-400" id="date@{{sher.date}}"></div>
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


