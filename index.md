---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
title: 🏠 Home
layout: home
nav_exclude: false
nav_order: 1
---

{% assign course_vars = site.data[site.data_folder].course %}
{% assign staff_vars = site.data[site.data_folder].staff %}
{% assign calendar = site.data[site.data_folder].calendar %}
{% assign staff = staff_vars[0] %} <!-- Cannot change this to instructor = because it will break the staffer.html include. If this needs to be instructor, then include.staff needs to be used as the variable in staffer.html  -->

# {{ site.tagline }}

{: .mb-2 }
{{ site.description }}
{: .fs-6 .fw-300 }

{{ course_vars.quarter }}
{: .md-badge-purple }

{{ course_vars.building }}
{: .md-badge-purple }

{{ course_vars.timings }}
{: .md-badge-purple }

{% include staffer.html staff=staff nobio='true' %}

{: .note }
Piazza and Gradescope are accessed through [Canvas](https://canvas.ucsd.edu/courses/77853/).

{: .important }
If you are joining the course late and would still like to earn full credit for assignments, please **[read this](https://docs.google.com/document/d/1weRix0H196EMKraKv68Ko_ByTbGMCCwIob7Wv70b8Pk/edit?tab=t.0)**! Please also note that I have **no control over the waitlist**. Please email [cogsadvising@ucsd.edu](mailto:cogsadvising@ucsd.edu) or drop in their office hours (your best bet)!

## Office Hours
* **Prof. T (Brendan)**:
  * Wednesdays 11:00AM-12:00PM @ CSB 259
  * Thursdays 2:00-3:00PM @ Zoom (link)
* **Lindsey Gu (TA)**: Mondays 1:00-2:00PM @ Zoom (link)
* **Emily Cheng (TA)**: Tuesdays 10:45-11:45AM @ Zoom (link)

<!-- **{{ course_vars.announcement.text }}** -->

## Schedule

<table class="schedule-table">
  <thead>
    <tr>
      <th class="col-week">Week</th>
      <th>Lecture Topics</th>
      <th>Due dates / Events</th>
      <th class="col-section">Section (Fri)</th>
    </tr>
  </thead>
  <tbody>
    {% for week in calendar %}
      {% include week.html week=week %}
    {% endfor %}
  </tbody>
</table>
