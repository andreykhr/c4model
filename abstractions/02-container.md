---
layout: default
title: 2. Контейнер
parent: Абстракции
nav_order: 2
permalink: /abstractions/container
---

# Контейнер

Не Docker! В модели C4 контейнер представляет собой приложение или хранилище данных. Контейнер - это то, что должно быть
запущено для работы всей программной системы. В реальном выражении контейнер - это что-то вроде:

- __Серверное веб-приложение__: веб-приложение Java EE, работающее на Apache Tomcat, ASP.NET Приложение MVC, работающее 
на Microsoft IIS, приложение Ruby on Rails, работающее на WEBrick, Node.js приложение и т.д.
- __Веб-приложение на стороне клиента__: приложение на JavaScript, работающее в веб-браузере с использованием Angular, 
Backbone.JS, jQuery и т.д.
- __Клиентское настольное приложение__: настольное приложение для Windows, написанное с использованием WPF, настольное 
приложение для OS X, написанное с использованием Objective-C, кроссплатформенное настольное приложение, написанное с 
использованием JavaFX, и т.д.
- __Мобильное приложение__: приложение для Apple iOS, приложение для Android, приложение для Microsoft Windows Phone 
и т.д.
- __Серверное консольное приложение__: автономное приложение (например, "общедоступное статическое основное приложение 
с пустым файлом"), пакетный процесс и т.д.
- __Бессерверная функция__: одна бессерверная функция (например, Amazon Lambda, функция Azure и т.д.).
- __База данных__: схема или база данных в системе управления реляционными базами данных, хранилище документов, 
графической базе данных и т.д., таких как MySQL, Microsoft SQL Server, Oracle Database, MongoDB, Riak, Cassandra, Neo4j 
и т.д.
- __Хранилище больших двоичных объектов или контента__: Хранилище больших двоичных объектов (например, Amazon S3, 
Microsoft Azure Blob Storage и т.д.) или сеть доставки контента (например, Akamai, Amazon CloudFront и т.д.).
- __Файловая система__: полная локальная файловая система или часть более крупной сетевой файловой системы (например, 
SAN, NAS и т.д.).
- __Shell script__: отдельный shell-скрипт, написанный на Bash и т.д.
- и так далее

Контейнер - это, по сути, граница среды выполнения, ограничивающая некоторый выполняемый код или некоторые сохраняемые 
данные. Название "контейнер" было выбрано потому, что я хотел, чтобы название ничего не указывало на физическую природу 
того, как выполняется этот контейнер. Например, один сервер Java EE, такой, как Apache Tomcat, может запускать несколько 
веб-приложений, внутри одной виртуальной машины Java, хотя каждое из этих веб-приложений по существу изолировано
от других. На этапе разработки у меня может быть три веб-приложения, запущенных на одном сервере Apache Tomcat,
в то время как каждое веб-приложение может быть развернуто на выделенном сервере Apache Tomcat в рабочей среде.
В этой ситуации каждое веб-приложение представляет собой "контейнер C4", а развертывание является отдельной задачей.

## ЧаВо

### Почему "контейнер"?

Такие термины, как "процесс", "приложение", "app", "сервер", "развертываемый модуль" и т.д., имеют соответствующие 
значения, поэтому название "контейнер" было выбрано как общий способ описания чего-либо, в чем находятся компоненты. 
С одной стороны, прискорбно, что контейнеризация стала популярной, потому что многие разработчики программного 
обеспечения теперь ассоциируют термин "контейнер" с Docker. С другой стороны, иногда существует хорошее соотношение 
между контейнером в модели C4 и инфраструктуре (например, Docker контейнер).

Хотя многие команды успешно используют модель C4 как есть, при необходимости вы можете изменить терминологию.

### Веб-приложения: один контейнер или два?

Если вы создаете серверное веб-приложение (например, Spring MVC, ASP.NET, Ruby on Rails, Django и т.д.), которое
преимущественно генерирует статический HTML-контент, тогда это единый контейнер. Если имеется значительное количество
JavaScript, предоставляемый серверным веб-приложением (например, одностраничным приложением, созданным с использованием
Angular), тогда это два контейнера.

Хотя во время развертывания серверное веб-приложение включает в себя как серверный, так и клиентский код,
рассмотрение клиента и сервера как двух отдельных контейнеров явно указывает на то, что это два отдельных пространства 
процессов, взаимодействующих через механизм межпроцессной/удаленной связи (например, JSON/HTTPS). Это также 
обеспечивает основу для увеличения масштаба каждого контейнера в отдельности, чтобы показать компоненты внутри них.

### Является ли Java JAR, сборка C#, библиотека DLL, модуль и т.д. контейнером?

Как правило, нет. Контейнер - это конструкция среды выполнения, подобная приложению; в то время как файлы Java JAR, 
сборки C#, библиотеки DLL, модули и т.д. используются для организации кода в этих приложениях.

### Следует ли представлять службы хранения данных в виде программных систем или контейнеров?

Часто задаваемый вопрос заключается в том, должны ли такие сервисы, как Amazon S3, Amazon RDS, база данных SQL Azure,
сети доставки контента и т.д., отображаться как программные системы или контейнеры. В конце концов, это внешние сервисы,
которыми большинство из нас не владеет и не управляет самостоятельно.

Если вы создаете программную систему, использующую Amazon S3 для хранения данных, это правда, что вы не запускаете S3 
самостоятельно, но у вас есть право собственности и ответственность за используемые корзины. Аналогично с Amazon RDS, 
у вас есть (более или менее) полный контроль над любыми создаваемыми вами схемами баз данных. По этой причине относитесь
к ним как к контейнерам, поскольку они являются неотъемлемой частью архитектуры вашего программного обеспечения, хотя и
размещены в другом месте.