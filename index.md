---
layout: splash # home
title: "XIII Workshop on Agents Applied in Healthcare"
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/logo-full.png
excerpt: "Part of the 20th International Conference on Autonomous Agents and Multiagent Systems"
intro: 
  - excerpt: 'The workshop aims to discuss applications of agent technologies to healthcare, a crucial domain of research, as demonstrated by the numerous initiatives devoted to financially supporting projects in this topic, such as those included under the “Health and Wellbeing” work programme of H2020 in Europe or promoted by the NIH in the USA.
They particularly motivate research devoted to finding solutions enabling an effective introduction of ICT in healthcare, as it is expected to have a big impact in expanding healthcare coverage while reducing its costs.
Topics like Healthy Ageing, Active Living, Chronic Disease Management, Patient Empowerment or others related to Quality of Life play an increasingly important role in this research.'
---

## Latest news

{% assign timeframe = 604800 %}
{% assign maxposts = 3 %}
{% assign date_format = site.minima.date_format | default: "%m/%d" %}

<ul class="post-list text-muted list-unstyled">
{% for post in site.posts limit: maxposts %}
  {% assign post_in_seconds = post.last_modified_at | date: "%s" | plus: 0 %}
  {% assign recent_posts = "now" | date: "%s" | minus: timeframe %}
  {% assign post_updated = post.last_modified_at | date: date_format %}
  {% capture post_date %}<small>{{ post.date | date: date_format }}</small>{% endcapture %}

  {% if post_in_seconds > recent_posts %}
  {% capture label_new %}<span class="label label-primary">new</span>{% endcapture %}
    {% if post.last_modified_at > post.date %}
      {% assign label_new = '' %}{% comment %}Clear NEW if modified{% endcomment %}
      {% capture label_updated %}<span class="label label-info">Updated <span class="badge">{{ post_updated }}</span></span>{% endcapture %}
    {% endif %}
  {% endif %}
  <li>
    <em>{{ post_date }}</em>
      <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}</a> {{ label_new }}{{ label_updated }}
    
  </li>
  {% assign post_date = '' %}
  {% assign label_updated = '' %}
{% endfor %}
</ul>

## Aims and scope

The workshop aims to discuss **applications of agent technologies to healthcare**, a crucial domain of research, as demonstrated by the numerous initiatives devoted to financially supporting projects in this topic, such as those included under the “Health and Wellbeing” work programme of H2020 in Europe or promoted by the NIH in the USA.
They particularly motivate research devoted to finding solutions enabling an effective introduction of ICT in healthcare, as it is expected to have a big impact in expanding healthcare coverage while reducing its costs.
Topics like Healthy Ageing, Active Living, Chronic Disease Management, Patient Empowerment or others related to Quality of Life play an increasingly important role in this research.

Besides these long-standing efforts, the recent global health situation caused by the COVID-19 pandemy both strengthened existing motivations for a digital transformation in healthcare and brought along new ones, by urging medical practitioners to embrace digital tools for delivering care to patients, and medical organisations and administrators to optimise resources usage as never before.
To overcome these new difficulties and deal with the long-standing ones as well, many technical issues have yet to be addressed, with the goal of providing medical practitioners at any organisational level (primary care, intensive care, administrators, etc.) the most suitable digital tools to support their day to day practice, introducing telemedicine to rethink processes and organisation of healthcare facilities.
Clinical decision support systems, adaptive and intelligent workflow management software, personal digital assistants, wearable technology ecosystems and the like are all tools with enormous potential benefits to deliver in the healthcare domain, for instance.

*Intelligent agent-based systems* constitute one of the most exciting research areas in Artificial Intelligence.
Due to the growing interest in the exploitation of agent-based systems in healthcare, a number of applications addressing clinical problems are already based on agent technology.
Thus, it is unquestionable that a benefit is guaranteed if the specialists in the field can meet and report on the results achieved in this area, discuss the advantages that agent-based systems may bring to medical domains, and possibly the problems they encountered, and also provide a list of the research topics that should be tackled in the near future.

## Focus

Core aspects of this workshop will be:
 - **Interdisciplinary research**: special efforts will be devoted to attract the attention of healthcare and biomedical specialists, so that they attend the workshop and realise the potential benefits of agent technology;
 - **Applied research**: the organising committee will also pay special attention to papers describing applications which are not just academic, but that are already deployed and running in a real medical environment;
 - Research devoted to **integrating agents with other technologies from the broad AI domain** will be particularly welcome, such as machine learning, multi-agent reinforcement learning, distributed planning.

Several methodological and technical problems have been discovered by the researchers that attempt to deploy agent-based systems in the medical area; just to name a few, the growing number of huge databases that need to be integrated (e.g. genetic data from next generation sequencing), the difficulty to integrate new agent-based systems with legacy software, the need to apply changing national and international laws and regulations concerning the privacy of medical data and the security of the transaction of patient information between agents.

## Target audience

The workshop is of interest to computer scientists applying agents in the healthcare field, and also for those looking for real application domains where their basic research can be deployed and for those looking for unsolved problems in the healthcare area that may be addressed using agent technology.
This workshop is relevant also for medical and biomedical practitioners who want to discover how agent technology may help them in their clinical tasks.
The workshop may attract both established scientists as well as postgraduates and PhD students, since there are many open fields of work in this area.
