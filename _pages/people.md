---
title: People
permalink: /people/
author_profile: true
redirect_from:
  - /people.html
---
{% include base_path %}

{% assign people_sorted = site.profiles | sort: 'joined' %}
{% assign role_array = "pi|postdoc|gradstudent|researchstaff|visiting|others|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h2>Postdoctoral Fellows</h2>
 {% elsif role == 'pi' %}
<h2>Principal Investigator</h2>
 {% elsif role == 'gradstudent' %}
<h2>Graduate Students</h2>
 {% elsif role == 'researchstaff' %}
<h2>Research Staff</h2>
 {% elsif role == 'visiting' %}
<h2>Visiting Scholars</h2>
 {% elsif role == 'others' %}
<h2>Honorary Members</h2>
 {% elsif role == 'alumni' %}
<h2>Alumni</h2>
{% endif %}
</div>


{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ site.baseurl }}{{ profile.url }}" rel="permalink"><img class="profile-thumbnail" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ site.baseurl }}{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <br>
          <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>


{% endif %}
{% endfor %}


| Alumni           | When were they here  | Where are they now                             |
| --------         | -------------------- | ---------------------------------------------- |
| Kyle S. Severson | 7/2013-11/2018 | Neuroscience Program Ph.D. student; currently postdoc at Duke University |
| Erik A. Finkel   | 9/2014-5/2019  | Neuroscience Program Ph.D. student; currently Data Scientist 1 at Leaseable |
| Duo Xu           | 6/2015-5/2020  | Neuroscience Program Ph.D. student; currently postdoc at UCSF |
| Hongdian Yang, PhD | 7/2012-6/2016 | postdoc; currently Assistant Professor in Dept. of Cell Biology and Neuroscience at UC Riverside, Riverside, CA. |
| Sung Eun Kwon, PhD | 10/2012-12/2017 | postdoc; currently Assistant Professor in Dept. of Molecular, Cellular and Developmental Biology at Univ. of Michigan, Ann Arbor. |
|  Genki Minamisawa, PhD | 7/2013-7/2019 | postdoc; currently Research Scientist at RIKEN Center for Brain Science, Japan. |
