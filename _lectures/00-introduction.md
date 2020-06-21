---
title: Introduction
description: Prerequisites and general info
lecture_number: 0
topic_number: 0
layout: lecture
mathjax: true
---
## What this wiki is

This wiki encapsulates the Math 104E calculus course at the University of Pennsylvania. 104E is a second semester calculus course presented for an engineering audience (hence the "E"). The goal of this wiki is to codify the content of this course in a way that is easily expandable or amendable as necessary, and to provide future teachers/students of the course with a lean, searchable text. The pages are in sequence (navigable from the home page or by using the arrows at the top and bottom of each page), and each page is designed to be a mini-lecture of about 10-15 minutes.

## Prerequisites

This course assumes that you have had a first semester calculus course (such as AP Calculus AB or Math 103 at Penn). You should be able to compute basic derivatives and integrals. Experience shows that some students may need to brush up on precalculus skills: factoring, exponent rules, logarithm rules, trigonometric functions and unit circle values, and graphing functions (among other things).

## Philosophy

This course focuses on the big picture over gritty calculations and memorized tricks. There will be some things you simply must commit to memory, but these will be few and highlighted in some way (yet to be determined). Also, a certain amount of practice is required to gain facility in the basic mechanics of calculus. For that, you should look to the big fat calculus text sold in the bookstore (at least until we have enough problems built into the wiki).

## Outline

These are the big topics covered, and the number of lectures per topic:
{% for topic in site.data.topics %}
{%- if forloop.first -%}{%- continue -%}{%- endif -%}
{%- if forloop.last -%}{%- continue -%}{%- endif -%}
{%- assign topic_index = forloop.index0 -%}
{% assign topic_lectures = site.lectures | where: "topic_number", topic_index %}
1. [{{ topic.name }}]({{ site.baseurl }}/#{{ topic.slug }}): {{ topic_lectures | size }} lectures
{%- endfor -%}
