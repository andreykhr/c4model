---
layout: default
title: Главная
nav_order: 1
description: C4 model
permalink: /
---

# Модель C4 для визуализации программной архитектуры

C4 модель является:

1. Набором [иерархических абстракций](/abstractions) (software systems, containers, components, and code).
2. Набором [иерархических диаграм](/diagrams) (system context, containers, components, and code).
3. [Не зависимым от нотации](/diagrams/notation).
4. [Не зависимым от инструментов](/tooling).

[![Обзок C4 модели для визуализации программной архитектуры](/images/c4-overview.png)](/images/c4-overview.png)

## Использование и преимущества

Модель C4 легка к изучению, удобный для разработчиков подход к построению диаграмм архитектуры программного обеспечения.
Хорошие программные архитектурные диаграммы помогают с коммуникацией внутри и снаружи программной разработки/продуктовых команды, эффективной адаптации новых сотрудников, архитектурного обзора/оценки, выясления рисков (таких как [risk-storming](https://riskstorming.com)),моделирование угроз, итд.

<table style="text-align: center">
<tr>
<td>
<iframe src="https://www.youtube-nocookie.com/embed/x2-rSnhpw0g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
<br />
<b>Визуализация программной архитектуры с C4 моделью</b>
<br />
Записано на "Agile on the Beach 2019", July 2019
</td>
<td>
<a href="https://leanpub.com/visualising-software-architecture"><img src="/images/book-small.png" width="150px" /></a>
<br />
<b>C4 модель для визуализации программной архитектуры</b>
<br />Simon Brown
</td>
</tr>
</table>

<script>
    const links = {
        'abstractions': '/abstractions',
        'systemcontextdiagram': '/diagrams/system-context',
        'containerdiagram': '/diagrams/container',
        'componentdiagram': '/diagrams/component',
        'codediagram': '/diagrams/code',
        'systemlandscapediagram': '/diagrams/system-landscape',
        'dynamicdiagram': '/diagrams/dynamic',
        'deploymentdiagram': '/diagrams/deployment',
        'notation': '/diagrams/notation',
        'tooling': '/tooling',
        'faq': '/faq',
    };
    var hash = window.location.hash;

    if (hash && hash.length > 0) {
        hash = hash.substring(1).toLowerCase();
        const link = links[hash];

        if (link) {
            window.location.href = link;
        }
    }
</script>