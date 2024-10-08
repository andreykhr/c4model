---
layout: default
title: Введение
nav_order: 2
permalink: /introduction
---

# Введение

Попросите кого-нибудь из представителей строительной отрасли визуально передать архитектуру здания и вам будут представлены
планы участка, планы этажей, вид с высоты, виды поперечного сечения и подробные чертежи. Напротив, попросите
разработчика программного обеспечения описать программную архитектуру программной системы с помощью диаграмм, и вы, скорее всего, получите
запутанное нагромождение прямоугольников и линий ... несогласованные обозначения (цветовое кодирование, формы, стили линий и т.д.), неоднозначные названия,
немаркированные связи, общая терминология, отсутствие выбора технологий, смешанные абстракции и т.д.

| ![Эскиз архитектуры программного обеспечения](/images/sketch-1.jpg) | ![Эскиз архитектуры программного обеспечения](/images/sketch-2.jpg) |
| ![Эскиз архитектуры программного обеспечения](/images/sketch-3.jpg) | ![Эскиз архитектуры программного обеспечения](/images/sketch-4.jpg) |

В нашей отрасли действительно есть унифицированный язык моделирования (UML), ArchiMate и SysML, но вопрос о том, обеспечивают ли они
эффективный способ передачи информации об архитектуре программного обеспечения, часто неуместен, поскольку многие команды уже отказались от них
в пользу гораздо более простых схем "прямоугольников и линий". Отказ от этих языков моделирования - это одно, но,
возможно, в гонке за гибкостью многие команды разработчиков программного обеспечения утратили способность к визуальному общению.

## Карты вашего кода

Модель C4 была создана для того, чтобы помочь командам разработчиков программного обеспечения описывать архитектуру программного обеспечения и обмениваться
информацией о ней как на начальных этапах проектирования, так и при ретроспективном документировании существующей кодовой базы. Это способ создания
"карт вашего кода" с различными уровнями детализации, аналогично тому, как вы использовали бы что-то вроде Google Maps для увеличения
или уменьшения масштаба интересующей вас области.

| ![](/images/map-4.jpg) | ![](/images/map-3.jpg) | ![](/images/map-2.jpg) | ![](/images/map-1.jpg) |
| ![](https://static.structurizr.com/workspace/36141/diagrams/SystemContext.png) | ![](https://static.structurizr.com/workspace/36141/diagrams/Containers.png) | ![](https://static.structurizr.com/workspace/36141/diagrams/Components.png) | ![](https://static.structurizr.com/workspace/36141/diagrams/MainframeBankingSystemFacade.png) |
| Уровеь 1: Диаграмма [системный контекст (system context)](/diagrams/system-context) обеспечивает отправную точку, показывающую, как данная программная система вписывается в окружающий мир. | Уровень 2: Диаграмма [контейнеров (container)](/diagrams/container) увеличивает масштаб системы программного обеспечения, показывая приложения и хранилища данных внутри нее. | Уровень 3: Диаграмма [компонентов (component)](/diagrams/component) увеличивает масштаб отдельного контейнера, показывая компоненты внутри него. | Уровень 4: Диаграмма [код (code)](/diagrams/code) (например, класс UML) может использоваться для увеличения масштаба отдельного компонента, показывая, как этот компонент реализован на уровне кода. |

## Повышение зрелости диаграмм

Цель модели C4 - повысить уровень зрелости, связанный с диаграммами архитектуры программного обеспечения.

<span style="color: black">Модель зрелости, представляющая собой диаграмму архитектуры программного обеспечения</span>
{: .text-beta}
<style>
    .table-wrapper {
        border-radius: 0;
    }
    table {
        border: 1px black solid;
        border-radius: 0;
        -webkit-border-horizontal-spacing: 0;
        -webkit-border-vertical-spacing: 0;
    }
    thead th {
        border-bottom: 0;
        border-left: 0;
        border-right: 1px black solid;

        color: white;
    }
    thead th:nth-child(5) {
        border-right: 0;
    }
    tbody td:nth-child(5) {
        border-right: 0;
    }
    td {
        border-right: 1px black solid;
        text-align: center;
        vertical-align: top;
        width: 20%;
    }
    th:nth-child(1) {
        background-color: #dc4430;
    }
    th:nth-child(2) {
        background-color: #e37334;
    }
    th:nth-child(3) {
        background-color: #e9cc49;
    }
    th:nth-child(4) {
        background-color: #95cb49;
    }
    th:nth-child(5) {
        background-color: #57ad51;
    }
    .maturity_label {
        font-weight: bold;
        color: black;
    }
    .maturity_text {
        font-size: 9px;
        color: black;
    }
</style>


<table>
    <thead>
        <tr>
            <th>Уровень 1</th>
            <th>Уровень 2</th>
            <th>Уровень 3</th>
            <th>Уровень 4</th>
            <th>Уровень 5</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <div class="maturity_label">Начальные</div>
                <div class="maturity_text">Никаких диаграмм архитектуры программного обеспечения.</div>
            </td>
            <td>
                <div class="maturity_label">Ad hoc</div>
                <div class="maturity_text">Диаграммы архитектуры программного обеспечения со специальными абстракциями и обозначениями в универсальном инструменте построения диаграмм.</div></td>
            <td>
                <div class="maturity_label">Определенный</div>
                <div class="maturity_text">Диаграммы архитектуры программного обеспечения с определенными абстракциями и обозначениями в универсальном инструменте построения диаграмм.</div></td>
            <td>
                <div class="maturity_label">Смоделированный</div>
                <div class="maturity_text">Диаграммы архитектуры программного обеспечения с определенными абстракциями и обозначениями, созданные вручную с помощью инструмента моделирования.</div></td>
            <td>
                <div class="maturity_label">Оптимизация</div>
                <div class="maturity_text">Элементы модели совместно используются командами по всей организации. - Модели используются в качестве наборов данных, доступных для запроса. - Автоматическое создание элементов модели из исходного кода, среды развертывания, журналов и т.д. - и т.п.</div>
            </td>
        </tr>
    </tbody>
</table>

<script type="application/javascript" src="https://code.jquery.com/jquery-3.7.1.slim.min.js"></script>
<script type="application/javascript" src="/assets/c4model.js"></script>