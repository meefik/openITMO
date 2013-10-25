semanticNT
==========

Цель образовательного проекта "Открытое онлайн-обучение" — предоставление доступа к электронным курсам [НИУ ИТМО](http://www.ifmo.ru/), которые могут содержать видеолекции, электронные презентации к ним, текстовые материалы, вопросы для самоконтроля, экзаменационные задания.

Познавайте новое в компактной форме в любой точке мира в удобное для себя время!

Описание
========

В проекте используется система, в основе которой лежит концепция веб-приложения. В отличие от веб-сайта, где сервером генерируется контент и отсылается клиенту в виде HTML-страниц, система представляет собой почти автономное приложение, работающее в браузере. Приложение динамически отслеживает свое состояние, обрабатывает действия пользователя и отображает данные, которые получает с сервера по запросу в формате [JSON](http://ru.wikipedia.org/wiki/JSON). В таком приложении страницы динамически изменяются на клиенте, а не генерируется полностью или частично на сервере. Стоит отметить, что все данные делятся на две части — статические и динамические. Предполагается, что данные не меняющиеся со временем (например, содержимое курса) хранятся в файлах на веб-сервере, а динамически изменяемые данные (например, данные пользователей) хранятся в базе данных, доступ к которым можно получить прямо из веб-приложения через [API](http://ru.wikipedia.org/wiki/API). Веб-приложение получает данные с сервера посредством службы [REST](http://ru.wikipedia.org/wiki/REST), представляющая собой некоторый API, используя который приложение может получать и передавать динамически изменяющиеся данные для последующей их обработки и сохранения в базе данных. Такой API в дальнейшем можно использовать при разработке других приложений, например приложения для мобильных устройств. 

При разработке системы используется только [свободное программное обеспечение](http://ru.wikipedia.org/wiki/Свободное_программное_обеспечение). Серверная архитектура спроектирована с учетом возможности масштабирования системы, что позволяет почти линейно наращивать вычислительную мощность путем увеличения количества серверных компонентов. В качестве серверной платформы используется [node.js](http://nodejs.org/), а в качестве front-end — веб-сервер [nginx](http://nginx.org/). 

Для хранения данных используется нереляционная ([noSQL](http://ru.wikipedia.org/wiki/NoSQL)) документо-ориентированная СУБД [MongoDB](http://www.mongodb.org/), основным достоинством которой является возможность работы с большими объемами данных, масштабируемость и распределенность. 

Разработка клиентской части (веб-приложение) ведется на основе фреймворка [AngularJS](http://angularjs.org/) и библиотеки [jQuery](http://jquery.com/), в качестве шаблона оформления (стили и примитивы) используется [Twitter Bootstrap](http://twitter.github.io/bootstrap/). В качестве видеоплеера используется [popcorn.js](http://www.popcornjs.org/).

Электронный курс состоит из отдельных блоков, каждый из которых представляет собой шаблон JavaScript + HTML + CSS. На данный момент в системе предусмотрены следующие типовые блоки: 

 * программа;
 * дорожная карта;
 * форумы и объявления;
 * видеолекции, презентации, опросы;
 * онтология предметной области;
 * проектная деятельность;
 * упражнения;
 * практикум;
 * песочница;
 * экзамен;
 * рейтинг.

Разработчики системы могут создавать новые типы блоков, если предложенного функционала недостаточно. Каждый блок содержит клиентскую и серверную части,  разработка которых должна вестись на JavaScript — один язык как для клиента, так и для сервера, что позволяет использовать одни и те же фрагменты кода на обеих сторонах. Помимо использования единого языка для программирования как клиентской, так и серверной части, следует упомянуть о наличии бесплатной облачной среды разработки [Cloud9](https://c9.io/), что является еще одним плюсом для разработчиков системы.

Лицензия
========

(с) НИУ ИТМО, 2013

Проект опубликован под лицензией [GPL версии 3](http://www.gnu.org/licenses/gpl-3.0.html) и выше. 

Адрес в Интернете: http://courses.academicmt.ru/

