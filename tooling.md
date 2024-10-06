---
layout: default
title: Инструменты
nav_order: 6
permalink: /tooling
---

# Инструменты

На занятиях по проектированию вы можете воспользоваться белой доской или флипчартом, которые лучше подходят для
совместной работы и быстрого выполнения итераций. Для долговременной документации существует ряд инструментов, которые
помогут создать диаграммы архитектуры программного обеспечения на основе модели C4. Вот некоторые из вопросов, которые
вы должны задать себе, рассматривая инструменты:

- Кто авторы диаграмм и насколько они технически подготовлены?
- Кто аудитория диаграмм и как они получат доступ к диаграммам/документации?
- [Построение диаграмм против моделирования?] (/tooling#построение диаграмм против моделирования)
- Интерфейс с "перетаскиванием" в сравнении с "диаграммами в виде кода"?
- Данные, хранящиеся в git рядом с вашим исходным кодом, по сравнению с данными, хранящимися в инструменте / облачном сервисе?
- Простые для сранвнения исходные тексты для использования в `pull requests`?
- Закрытый формат данных или открытый формат данных?
- Интерактивные диаграммы или статические диаграммы?
- Бесплатный или платный?
- Закрытый или с открытым исходным кодом?
- Облачный или автономный?
- Коротко или долго живущая документация?
- Построение диаграмм только для команды или моделирование в масштабах предприятия?

## Построение диаграмм или моделирование

Небольшое замечание о сравнении построения диаграмм и моделирования, поскольку это самое важное решение, которое вам
нужно будет принять в отношении инструментов. Модель C4 *может* использоваться независимо от того, используете ли вы
инструмент для построения диаграмм или моделирования, но при переходе от построения диаграмм к моделированию открываются
некоторые интересные возможности.

### Построение диаграмм

Как отрасль, мы, как правило, предпочитаем построение диаграмм (например, Visio, draw.io, Lucidchart, PlantUML, Mermaid и т.д.)
над моделированием (например, Sparx EA, Archi, Ice Panel, Structurizr и т.д.), в первую очередь потому, что барьер для входа относительно
низок, и это рассматривается как гораздо более простая задача. Но существует ряд серьезных проблем, связанных с использованием инструментов построения диаграмм для
построения диаграмм архитектуры программного обеспечения:

1. Язык предметной области инструментов построения диаграмм - "прямоугольники и линии", что означает:
   - Они не могут предоставить никакой помощи или проверки правильности ваших диаграмм.
   - Вы не можете запрашивать диаграммы (например, "покажите мне все зависимости компонента X").
2. Повторное использование элементов диаграммы осуществляется с помощью копирования и вставки - если вы переименовываете поле, вам нужно переименовать его на каждой диаграмме, где оно появляется.
3. Многие инструменты построения диаграмм имеют трудно различимые форматы данных, что затрудняет их использование, например, в сочетании с `Pull requests`.

### Моделирование

С помощью инструмента моделирования вы создаете не визуальную модель архитектуры вашего программного
обеспечения (единое определение всех элементов и взаимосвязей между ними), а затем создаете различные представления
(которые становятся диаграммами) поверх этой модели. Это требует немного большей тщательности, но проблемы могут быть решены -
инструменты моделирования могут понять семантику того, что вы пытаетесь сделать, оказать дополнительную помощь,
а переименование элементов / связей выполняется легко.

Модели архитектуры программного обеспечения, по сути, представляют собой просто [ориентированные графы](https://en.wikipedia.org/wiki/Directed_graph),
состоящие из узлов и ребер, с диаграммами, показывающими подмножество графа. Как только вы увидите разделение модели
(которая представляет собой просто структурированные данные) и представлений (которые отображаются в виде диаграмм),
вы сразу поймете, что перед вами открывается целый ряд интересных возможностей:

- Создание альтернативных визуализаций, помогающих понять большие и сложные архитектурные модели - подробнее см. в разделе [Масштабируется ли модель C4?](/faq#масштабируется-ли-модель-c4).
- Запрос модели.
- Экспорт модели в другие инструменты.
- и так далее

Модель - это всего лишь данные! И мы, как разработчики программного обеспечения, располагаем бесконечным набором
инструментов для визуализации этих данных и управления ими.

## Варианты

Вот набор инструментов, которые обеспечивают некоторую специфическую поддержку модели C4.

<script type="application/javascript" src="https://code.jquery.com/jquery-3.7.1.slim.min.js"></script>

<style>
.toolingOptionFilter {
    margin: 10px 20px 20px 10px;
    display: inline-block;
}
.toolingOption {
    font-size: 16px;
    display: inline-block;
    margin: 10px;
    border: solid 1px #1168BD;
    padding: 5px 10px 5px 10px;
    border-radius: 5px;
}
.toolingOption:hover {
    background: #1168BD;
    color: #ffffff;
}
.toolingOption:hover a {
    color: #ffffff;
}
.toolingOption a {
    text-decoration: none;
}
.toolingOption a:hover {
    background: #1168BD;
    color: #ffffff;
    text-decoration: none;
}
.centered {
    text-align: center;
}
.faded {
    opacity: 0.2;
}
.small {
    font-size: 13px;
}
.smaller {
    font-size: 11px;
}
</style>

<table>
<tr>
<td style="vertical-align: top">
    <h4>Поддерживаемые типы диаграмм</h4>
    <div class="toolingOptionFilter">
        <label><input id="toolingStaticDiagramsFilter" type="checkbox" checked="checked" disabled="disabled"> Статические диаграммы</label>
        <div class="smaller">(например, системный контекст, схемы контейнеров и компонентов)</div>
    </div>

    <div class="toolingOptionFilter">
        <label><input id="toolingDynamicDiagramsFilter" type="checkbox"> Динамические диаграммы</label>
        <div class="smaller">(например, диаграммы совместной работы или последовательности действий)</div>
    </div>

    <div class="toolingOptionFilter">
        <label><input id="toolingDeploymentDiagramsFilter" type="checkbox"> Диаграммы развертывания</label>
        <div class="smaller">(например, диаграммы, показывающие проблемы с развертыванием и инфраструктурой)</div>
    </div>
</td>
<td style="vertical-align: top">
    <h4>Диаграммы или моделирование</h4>
    <div class="toolingOptionFilter">
        <label><input id="toolingDiagrammingFilter" name="diagramVsModel" type="radio"> Инструмент для построения диаграмм</label>
        <div class="smaller">(то есть инструмент моделирования - для автоматической синхронизации нескольких диаграмм при переименовании элементов)</div>
    </div>

    <div class="toolingOptionFilter">
        <label><input id="toolingModelBasedFilter" name="diagramVsModel" type="radio" checked="checked"> Повторное использование элементов на нескольких диаграммах</label>
        <div class="smaller">(то есть инструмент моделирования - для автоматической синхронизации нескольких диаграмм при переименовании элементов)</div>
        <div style="margin-top: 10px">
        <span class="smaller" style="font-weight: normal; background: #02b621; color: #ffffff; padding: 5px; margin-top: 10px;">Рекомендуемый</span>
        </div>
    </div>
</td>
<td style="vertical-align: top">
    <h4>Авторство</h4>
    <div class="toolingOptionFilter">
        <label><input id="toolingWithUIFilter" name="authoring" type="radio"> Графический интерфейс пользователя</label>
        <div class="smaller">(пользовательский интерфейс моделирования перетаскиванием)</div>
    </div>

    <div class="toolingOptionFilter">
        <label><input id="toolingAsCodeFilter" name="authoring" type="radio" checked="checked"> Диаграммы и модели в виде кода</label>
        <div class="smaller">(для упрощения контроля версий и интеграции в конвейеры сборки/ другие инструменты)</div>
    </div>
</td>
<td style="vertical-align: top">
    <h4>Другое</h4>
    <div class="toolingOptionFilter">
        <label><input id="toolingOpenSourceFilter" type="checkbox"> С открытым исходным кодом</label>
        <div class="smaller">(бесплатно, разветвлять / настраивать и т.д.)</div>
    </div>

    <div class="toolingOptionFilter">
        <label><input id="toolingRenderingToolIndependentFilter" type="checkbox"> Независимый инструмент рендеринга</label>
        <div class="smaller">(для визуализации диаграмм с помощью различных инструментов или форматов визуализации, таких как <a href="/диаграммы/обозначения#альтернативные визуализации">диаграммы, графики и т.д.</a>)</div>
    </div>
</td>
</tr>
</table>

<div class="centered">
    <div class="toolingOption toolingOpenSource toolingModelBased toolingWithUI toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://www.archimatetool.com/blog/2020/04/18/c4-model-architecture-viewpoint-and-archi-4-7/" target="_blank">Archi</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams">
        <a href="https://github.com/lonely-lockley/archinsight" target="_blank">Archinsight</a>
    </div>
    <div class="toolingOption toolingModelBased toolingWithUI toolingStaticDiagrams toolingDeploymentDiagrams">
        <a href="https://www.archipeg.com/learn/c4-model-v1-metamodel" target="_blank">Archipeg</a>
    </div>
    <div class="toolingOption toolingModelBased toolingWithUI toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/ChangeVision/astah-c4model-plugin" target="_blank">Astah</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/plantuml-stdlib/C4-PlantUML" target="_blank">C4-PlantUML</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://adrianvlupu.github.io/C4-Builder" target="_blank">c4builder</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams">
        <a href="https://github.com/SlavaVedernikov/C4InterFlow" target="_blank">C4InterFlow</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/8T4/c4sharp" target="_blank">C4Sharp</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams">
        <a href="https://owulveryck.github.io/cue4puml4c4/" target="_blank">CUE4Puml4C4</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams">
        <a href="https://diagrams.mingrammer.com/docs/nodes/c4" target="_blank">Diagrams</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingWithUI toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://www.diagrams.net/blog/c4-modelling" target="_blank">diagrams.net</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://libraries.excalidraw.com/#dmitry-burnyshev-c4-architecture" target="_blank">Excalidraw</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://www.figma.com/templates/c4-model-examples/" target="_blank">Figma</a>
    </div>
    <div class="toolingOption toolingWithUI toolingOpenSource toolingModelBased toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://gaphor.org" target="_blank">Gaphor</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://www.gliffy.com/blog/c4-model" target="_blank">Gliffy</a>
    </div>
    <div class="toolingOption toolingWithUI toolingModelBased toolingStaticDiagrams toolingDynamicDiagrams">
        <a href="https://icepanel.io/c4-model" target="_blank">IcePanel</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://keadex.dev/en/projects/keadex-mina" target="_blank">Keadex Mina</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://www.lucidchart.com/pages/templates/c-4-model-example" target="_blank">Lucidchart</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/pihalve/c4model-visio-stencil" target="_blank">Microsoft Visio</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingDiagramming toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://mermaid.js.org/syntax/c4.html" target="_blank">Mermaid</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://miro.com/miroverse/c4-architecture/" target="_blank">Miro</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/goadesign/model" target="_blank">Model</a>
    </div>
    <div class="toolingOption toolingWithUI toolingModelBased toolingStaticDiagrams">
        <a href="https://supportportal.moodinternational.com/hc/en-us/articles/360015465100-MooD-and-the-C4-model" target="_blank">MooD</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://architecture.models.nasdanika.org/references/eSubpackages/c4/index.html" target="_blank">Nasdanika Architecture</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://stenciltown.omnigroup.com/stencils/c4/" target="_blank">OmniGraffle</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/soulspace-org/overarch" target="_blank">Overarch</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/DrMarkusVoss/pumla/blob/main/test/examples/C4example/pumlaC4Example.md" target="_blank">pumla</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams">
        <a href="https://github.com/nielsvanspauwen/pystructurizr" target="_blank">PyStructurizr</a>
    </div>
    <div class="toolingOption toolingWithUI toolingModelBased toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="http://www.sparxsystems.eu/c4/" target="_blank">Sparx Enterprise Architect</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingStaticDiagrams">
        <a href="https://rdbmodel.github.io" target="_blank">RDB modeling</a>
    </div>
    <div class="toolingOption toolingOpenSource toolingModelBased toolingAsCode toolingRenderingToolIndependent toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://structurizr.com" target="_blank">Structurizr</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://online.visual-paradigm.com/diagrams/features/c4-model-tool/" target="_blank">Visual Paradigm</a>
    </div>
    <div class="toolingOption toolingWithUI toolingDiagramming toolingStaticDiagrams toolingDynamicDiagrams toolingDeploymentDiagrams">
        <a href="https://github.com/Ferhat67/C4-yEd" target="_blank">yEd</a>
    </div>
</div>

<script>
    $('#toolingOpenSourceFilter, #toolingDiagrammingFilter, #toolingModelBasedFilter, #toolingAsCodeFilter, #toolingWithUIFilter, #toolingRenderingToolIndependentFilter, #toolingStaticDiagramsFilter, #toolingDynamicDiagramsFilter, #toolingDeploymentDiagramsFilter').change(function() {
        filterToolingOptions();
    });

    function filterToolingOptions() {
        var classes = '';

        if ($('#toolingOpenSourceFilter').is(":checked")) {
            classes = classes + '.toolingOpenSource';
        }
        
        if ($('#toolingDiagrammingFilter').is(":checked")) {
            classes = classes + '.toolingDiagramming';
        }
        
        if ($('#toolingModelBasedFilter').is(":checked")) {
            classes = classes + '.toolingModelBased';
        }
        
        if ($('#toolingAsCodeFilter').is(":checked")) {
            classes = classes + '.toolingAsCode';
        }
        
        if ($('#toolingWithUIFilter').is(":checked")) {
            classes = classes + '.toolingWithUI';
        }
        
        if ($('#toolingRenderingToolIndependentFilter').is(":checked")) {
            classes = classes + '.toolingRenderingToolIndependent';
        }
        
        if ($('#toolingStaticDiagramsFilter').is(":checked")) {
            classes = classes + '.toolingStaticDiagrams';
        }
        
        if ($('#toolingDynamicDiagramsFilter').is(":checked")) {
            classes = classes + '.toolingDynamicDiagrams';
        }
        
        if ($('#toolingDeploymentDiagramsFilter').is(":checked")) {
            classes = classes + '.toolingDeploymentDiagrams';
        }
        
        if (classes.length === 0) {
            $('.toolingOption').removeClass('faded');
        } else {
            $('.toolingOption').addClass('faded');
            $('.toolingOption').filter(classes).removeClass('faded');
        }
    }

    filterToolingOptions();
</script>
