---
layout: page
permalink: /teaching/
title: teaching
description: A comprehensive list of my teaching activities.
nav: false
nav_order: 10
sections: ["courses", "teaching support", "lectures", "seminars"]
---

<div class="post">
<article>
<div class="teaching">
    {% for sec in page.sections %}
        <h2 class="category">{{sec}}</h2>
        {% assign categorized_teach = site.teaching | where: "category", sec %}
        {% assign sorted_teach = categorized_teach | sort: "last_year" | reverse %}
        {% for teach in sorted_teach %}
        <div class="row teach-row">
            <div class="abbr">
                {%- for year in teach.years -%}
                    <abbr class="badge">{{ year }}</abbr>
                {%- endfor -%}
                {%- if teach.it_title -%}
                    <h2>{{teach.it_title}}</h2>
                    <h5><i>{{teach.title}}</i></h5>
                {%- else -%}
                    <h2>{{teach.title}}</h2>
                {%- endif -%}
                {%- if teach.course -%}
                    {%- if teach.site -%}
                        <a href="{{teach.site}}">{{ teach.course }}</a>
                    {%- else -%}
                        {{ teach.course }}
                    {%- endif -%}
                {%- endif -%}
                <div><span class=""><b>{{ teach.university }}</b></span>
                </div>
                {%- if teach.moodle -%}
                    <div class="links">
                    <a href="{{ teach.moodle }}" class="bibtex btn btn-sm z-depth-0 waves-effect waves-light" role="button">Moodle page</a>
                    </div>
                {%- endif -%}
                {%- if teach.slides %}
                    <div class="links">
                    <a href="{{ teach.slides }}" class="bibtex btn btn-sm z-depth-0 waves-effect waves-light" role="button">Slides</a>
                    </div>
                {%- endif %}
            </div>
        </div>
        {% endfor %}
    {% endfor %}
</div>
</article>
</div>