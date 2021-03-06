[<< Composer](02-composer.md) | [HTTP >>](04-http.md)

### Обработчик ошибок

Первый пакет который мы установим, будет перехватывать исключения и выводить отладочную информацию на экран. Мне нравится [filp/whoops](https://github.com/filp/whoops) и сейчас я покажу как подключить данный пакет к нашему проекту. Вы можете использовать любой другой пакет, который вам по душе. Как альтернативу можно использовать [PHP-Error](https://github.com/JosephLenton/PHP-Error).

Чтобы установить нужный нам пакет, зайдите в `composer.json` и добавьте его имя в блок "require":

```php
"require": {
    "php": ">=7.0.0",
    "filp/whoops": "~2.1"
},
```
Теперь запустите `composer update` из консоли.

Пока мы не можем использовать наши пакеты, так как PHP не умеет искать файлы классов самостоятельно. Данную проблему решает автозагрузчик классов. К счастью composer позаботился об автозагрузке за нас, нам нужно только добавить строку `require __DIR__ . '/../vendor/autoload.php';` в `Bootstrap.php`.

**Важно:** Никогда не выводите детальную информацию об ошибке в production среде. Трассировка стека или даже просто сообщение об ошибке могут помочь кому-то получить доступ к системе. Пользователю можно показать страничку с кодом ошибки, а детальную информацию записать в лог и отправить письмо с ошибкой на почту.

Для development среды отправка письма и запись в лог не имеет смысла - достаточно получить страницу с детальным описанием ошибки. Хорошей практикой является настройка среды из программного кода. На данном этапе мы можем установить `development` как рабочую среду.

После регистрации обработчика ошибок, попробуем сгенерировать исключение `Exception`, чтобы убедиться что все работает корректно. Добавим в`Bootstrap.php` следующий код:

```php
<?php declare(strict_types = 1);

namespace Example;

require __DIR__ . '/../vendor/autoload.php';

error_reporting(E_ALL);

$environment = 'development';

/**
* Register the error handler
*/
$whoops = new \Whoops\Run;
if ($environment !== 'production') {
    $whoops->pushHandler(new \Whoops\Handler\PrettyPageHandler);
} else {
    $whoops->pushHandler(function($e){
        echo 'Todo: Friendly error page and send an email to the developer';
    });
}
$whoops->register();

throw new \Exception;

```
Если после открытия страницы в барузере вы видете детальное описание ошибки, значит все работает должным образом.

[<< Composer](02-composer.md) | [HTTP >>](04-http.md)
