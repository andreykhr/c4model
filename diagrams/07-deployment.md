---
layout: default
title: Диаграмма развертывания
parent: Диаграммы
nav_order: 7
permalink: /diagrams/deployment
---

# Диаграмма развертывания

Диаграмма развертывания позволяет проиллюстрировать, как экземпляры программных систем и/или контейнеров в статической модели
развертываются в инфраструктуре в рамках заданной среды развертывания (например, производственная, промежуточная, 
разработка и т.д.). Он основан на [схеме развертывания UML](https://en.wikipedia.org/wiki/Deployment_diagram).

__Узел развертывания__ представляет, где запущен экземпляр программной системы/контейнера;
возможно, физическая инфраструктура (например, физический сервер или устройство), виртуализированная инфраструктура
(например, IaaS, PaaS, виртуальная машина), контейнеризированная инфраструктура (например, контейнер Docker),
среда выполнения (например, сервер баз данных, сервер веб-приложений Java EE, Microsoft IIS) и т.д.
Узлы развертывания могут быть вложенными.

Вы также можете захотеть включить __узлы инфраструктуры__, такие как службы DNS, балансировщики нагрузки, брандмауэры
и т.д.

Не стесняйтесь использовать значки, предоставляемые Amazon Web Services, Azure и т.д., для дополнения ваших диаграмм 
развертывания... просто убедитесь, что все используемые вами значки включены легенду вашей диаграммы.

## Пример 1

[![A deployment diagram](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment.png)](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment.png)

### Легенда диаграммы

[![A diagram key](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment-key.png)](https://static.structurizr.com/workspace/36141/diagrams/LiveDeployment-key.png)

## Пример 2

[![A deployment diagram](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment.png)](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment.png)

### Легенда диаграммы

[![A diagram key](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment-key.png)](https://static.structurizr.com/workspace/54915/diagrams/AmazonWebServicesDeployment-key.png)

## Область видимости

Одна или несколько программных систем в рамках единой среды развертывания (например, производственная, промежуточная, 
разработка и т.д.).

## Основные и вспомогательные элементы

Узлы развертывания, экземпляры программных систем и экземпляры контейнеров.

## Поддерживающие элементы

Узлы инфраструктуры, используемые при развертывании программной системы.

## Целевая аудитория

Технические специалисты как внутри, так и за пределами команды разработчиков программного обеспечения, включая 
архитекторов программного обеспечения, разработчиков инфраструктуры и персонал операционной службы/службы поддержки.

## Рекомендуется?

Да.

<script type="application/javascript" src="https://code.jquery.com/jquery-3.7.1.slim.min.js"></script>
<script type="application/javascript" src="/assets/c4model.js"></script>