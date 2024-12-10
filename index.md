---
layout: home
---

本wiki用于记录tkchu在游戏策划职业生涯中遇到的各种游戏机制。

> 游戏设计中「系统、机制、玩法、架构」等专业术语有什么不同？

- 机制：游戏中的基础规则。《守望先锋》中，路霸向前扔出铁链，如果击中敌方单位，则将敌方单位拉至路霸面前，并迫使对方面对路霸。这就是一个机制，它涉及游戏中会发生什么。
- 玩法：游戏中能玩家感到有趣快乐的规则组合，一般会与胜利相关。路霸钩中对手后，左键爆头接近战可以击杀脆皮单位，这套连招就可视为一个玩法。它提供了一个目标，而玩家的水平决定了目标是否可以达成。
- 系统：游戏中带有积累的成长性部分。路霸可能有各种各样的皮肤，需要玩家开箱子获得。皮肤及其获取可以视为一个皮肤系统。它通常需要玩家多日的参与，通过完成一个个子目标来达成最终目标。
- 架构：游戏中各系统的交互关系。比如在回合制战斗游戏中，可能会将50%的攻击力分给等级，将45%的攻击力分给装备，最后5%分给羁绊，这就是一种架构，决定了各个系统对总攻击力的贡献。

{% assign today = site.time | date: '%s' %}
{% assign start = '01-09-2020 00:00:00' | date: '%s' %}
{% assign secondsSince = today | minus: start %}
{% assign daysSince = secondsSince | divided_by: 24 | divided_by: 60 | divided_by: 60 %}

{% assign counter = 0 %}
{% for post in site.posts %}
{% unless item.published == false %}{% assign counter=counter | plus:1 %}{% endunless %}
{% endfor %}

{% assign needToWrite = daysSince | minus: counter %}

<ul>
{% for cat in site.categories %}
    <li>{{ cat[0] }} ({{ cat[1].size }})</li>
{% endfor %}
</ul>

<ol>
{% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.date | date: "%Y-%m-%d" }} {{ post.title }}</a>
    </li>
{% endfor %}
</ol>