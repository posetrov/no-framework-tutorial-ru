## Руководство по созданию PHP приложения без фреймворков [[Перевод](https://github.com/PatrickLouys/no-framework-tutorial)]

### Введение

Данное руководство предназначено для тех, кто хорошо знаком с PHP, а также с азами ООП. Прежде чем двигаться дальше, рекомендую ознакомится с принципами [SOLID](https://ru.wikipedia.org/wiki/SOLID_(%D0%BE%D0%B1%D1%8A%D0%B5%D0%BA%D1%82%D0%BD%D0%BE-%D0%BE%D1%80%D0%B8%D0%B5%D0%BD%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B5_%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5)), если вы еще не знакомы с ними.

Я видел как многие задавали вопросы в чат-руме на Stack Overflow, насколько хорош фреймворк X и стоит ли использовать его в своих проектах. В большинстве случаев ответ заключался в том, что они должны просто использовать PHP, а не фреймворк. Такой ответ является крайне неприятным, так как многие не знают с чего начать.

Моя цель заключается в создании ресурса, который послужил бы отправной точкой для разработчиков, задающихся вопросом о построении PHP приложения без фреймворков. В некоторых случаях использование фреймворка бессмысленно, и писать приложение с нуля, используя лишь сторонние пакеты, намного проще.

**Данный мануал был написан для версии PHP 7.0 или более поздних версий.** Перед тем как мы начнем, обновите PHP, если вы используете версию ниже 7.0. Я рекомендую использовать [текущую стабильную версию](http://php.net/downloads.php).

Ну что, [начнем](01-front-controller.md).

### Разделы

1. [Точка входа](01-front-controller.md)
2. [Composer](02-composer.md)
3. [Обработчик ошибок](03-error-handler.md)
4. [HTTP](04-http.md)
5. [Маршрутизатор](05-router.md)
6. [Контроллер](06-controller.md)
7. [Инверсия управления](07-inversion-of-control.md)
8. [Инъектор зависимостей](08-dependency-injector.md)
9. [Шаблонизация](09-templating.md)
