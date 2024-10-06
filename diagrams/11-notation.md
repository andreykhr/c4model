---
layout: default
title: Нотация
parent: Диаграммы
nav_order: 11
permalink: /diagrams/notation
---

# Нотация

Модель C4 не зависит от нотации и не предписывает каких-либо конкретных обозначений. Однако в качестве отправной точки
можно использовать простую нотацию, которая хорошо работает на досках, бумаге, стикерах, картотеках и различных
инструментах построения диаграмм.

Затем вы можете использовать цвет и формы для дополнения диаграммы, либо для добавления дополнительной информации, либо
для придания диаграмме более эстетичного вида. Хотя вы можете увидеть множество примеров диаграмм и инструментов, в 
которых используются синие и серые прямоугольники<sup>1</sup>, это не то, что диктуется моделью C4, и вы можете 
использовать какие угодно цвета, которые вам нравятся!

## Элементы

| [![Person](/images/notation-person.png)](/images/notation-person.png) | [![Software system](/images/notation-software-system.png)](/images/notation-software-system.png) |
| [![Container](/images/notation-container.png)](/images/notation-container.png) | [![Component](/images/notation-component.png)](/images/notation-component.png) |

Обратите внимание, что в каждом поле указан тип элемента/абстракции ("Человек", "Программная система", "Контейнер", 
"Компонент") - это целенаправленное решение, которое помогает устранить любую двусмысленность в отношении того, какой
уровень абстракции отображается.

## Отношения

| [![Relationship](/images/notation-relationship.png)](/images/notation-relationship.png) |

### Легенда диаграммы

Любая используемая нотация должна быть настолько понятной, насколько это возможно, но все диаграммы должны иметь 
легенду с обозначениями, чтобы сделать нотацию понятной. Это относится и к диаграммам, созданным с использованием таких
обозначений, как UML, ArchiMate и SysML, поскольку не все будут знать используемую нотацию.

[![A diagram key](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)](https://static.structurizr.com/workspace/36141/diagrams/Containers-key.png)

## Нотация, нотация, нотация

Несмотря на то, что модель C4 основана на абстракции и не зависит от нотации, вам все равно необходимо убедиться, что 
ваши обозначения на диаграммах имеют смысл и что диаграммы понятны. Хороший способ поразмыслить над этим - спросить
себя, может ли каждая диаграмма быть самостоятельной и понятной (в основном) без пояснений. Вы можете воспользоваться 
этим кратким обзором [контрольный список для проверки диаграмм архитектуры программного обеспечения](/diagrams/checklist),
чтобы помочь.

Вот несколько общих рекомендаций, связанных с обозначениями.

### Диаграммы

- Каждая диаграмма должна иметь заголовок, описывающий тип диаграммы и область ее применения (например, "Диаграмма системного контекста для моей программной системы").
- Каждая диаграмма должна иметь легенду, объясняющую используемые обозначения (например, формы, цвета, стили границ, типы линий, начертания стрелок и т.д.).
- Акронимы и сокращения (бизнес/домен или технология) должны быть понятны всем аудиториям или объясняться в ключе/условных обозначениях диаграммы.

### Элементы

- Тип каждого элемента должен быть четко указан (например, Человек, Программная система, контейнер или компонент).
- Каждый элемент должен иметь краткое описание, чтобы обеспечить "беглым взглядом" представление о ключевых обязанностях.
- Для каждого контейнера и компонента должна быть четко указана технология.

### Отношения

- Каждая линия должна представлять собой однонаправленную связь.
- Каждая строка должна быть помечена так, чтобы она соответствовала направлению и цели взаимосвязи (например, зависимости или потоку данных). Старайтесь использовать как можно более конкретную маркировку, в идеале избегая отдельных слов, таких как "Использование".
- Отношения между контейнерами (обычно они представляют собой межпроцессное взаимодействие) должны быть четко обозначены технологией/протоколом.

## C4 и UML

Хотя примеры диаграмм созданы с использованием нотации "прямоугольники и линии", основные диаграммы могут быть проиллюстрированы
с помощью UML с соответствующим использованием пакетов, компонентов и стереотипов. Однако результирующим диаграммам UML,
как правило, не хватает такого же количества описательного текста, поскольку добавить такой текст невозможно (или просто)
с помощью некоторых инструментов UML.

Вот три примера системного контекста, контейнера и схемы компонентов для сравнения.

| System context diagram                                                                                                                  | Container diagram                                                                                                          | Component diagram                                                                                                          |
|-----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------|
| [![System context diagram](/images/spring-petclinic-system-context.png)](/images/spring-petclinic-system-context.png)                   | [![Container diagram](/images/spring-petclinic-containers.png)](/images/spring-petclinic-containers.png)                   | [![Component diagram](/images/spring-petclinic-components.png)](/images/spring-petclinic-components.png)                   |
| [![System context diagram](/images/spring-petclinic-system-context-plantuml.png)](/images/spring-petclinic-system-context-plantuml.png) | [![Container diagram](/images/spring-petclinic-containers-plantuml.png)](/images/spring-petclinic-containers-plantuml.png) | [![Component diagram](/images/spring-petclinic-components-plantuml.png)](/images/spring-petclinic-components-plantuml.png) |
| [![System context diagram](/images/spring-petclinic-system-context-staruml.png)](/images/spring-petclinic-system-context-staruml.png)   | [![Container diagram](/images/spring-petclinic-containers-staruml.png)](/images/spring-petclinic-containers-staruml.png)   | [![Component diagram](/images/spring-petclinic-components-staruml.png)](/images/spring-petclinic-components-staruml.png)   |


## C4 и ArchiMate

Смотрите [C4 Model, Architecture Viewpoint и Archi 4.7](https://www.archimatetool.com/blog/2020/04/18/c4-model-architecture-viewpoint-and-archi-4-7/)
для получения подробной информации о том, как создавать диаграммы моделей C4 с помощью ArchiMate.

## Альтернативные визуализации

Наконец, не думайте, что вам всегда нужно использовать традиционную диаграмму в виде прямоугольников и стрелок.
Хотя обычно это стандартный подход, существуют и другие, часто интерактивные, визуализации, которые можно
использовать для отображения одних и тех же абстракций модели C4 совершенно разными способами.


| [![](/images/alternative-1.png)](https://structurizr.com/dsl?example=microservices)                   | [![](/images/alternative-2.png)](https://structurizr.com/dsl?example=microservices&renderer=graph)                                                 | [![](/images/alternative-3.png)](https://structurizr.com/dsl?example=microservices&renderer=ilograph)                                          |
| Traditional "boxes and arrows" diagrams are the default approach for documentation and presentations. | A D3.js force-directed graph is a very concise way to visualise larger software architectures, also providing an easy way to explore dependencies. | Ilograph's interactive diagrams provide a way to selectively zoom in and out, allowing you to explore your entire software architecture model. |

- <sup>1</sup> "C4 = синие и серые прямоугольники" - распространенное заблуждение, поэтому примеры диаграмм,
представленные на этом веб-сайте, теперь чередуются между синей, зеленой и красной версиями!

<script type="application/javascript" src="https://code.jquery.com/jquery-3.7.1.slim.min.js"></script>
<script type="application/javascript" src="/assets/c4model.js"></script>