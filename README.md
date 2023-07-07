<p align="center">
    <h1 align="center">Fastlogs PHP SDK</h1>
    <br>
</p>

Требования
------------

PHP 5.6+, установленные расширения json и curl.

Установка
---------------

1. Добавить в composer.json репозиторий:
```bash
{
    ....
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/King-Bird-Studio/fastlogs-sdk-php.git"
        }
    ],
    .....
}
```
2. Подключить к проекту:
```bash
composer require "fastlogs/sdk:dev-main"
```


Инициализация параметров
-------------------

Параметры подключения к сервису можно либо задавать в конструкторе отправки, либо определить в переменных окружения.

Пример определения параметров через переменные окружения:

```bash
# адрес сервера fastlogs
FASTLOGS_URL=https://fastlogs-backend.i.kingbird.ru

# SLUG лога, в который ведется запись
FASTLOGS_SLUG=slkr23r9fjls
```

Через конструктор:

```php
use fastlogs\sdk\Sender;

$sender = new Sender('slkr23r9fjls');
```

Использование
------------

```php
use fastlogs\sdk\Sender;

$sender = new Sender();

$data = [123, 456, 'sldfkjsf'];
$sender->add($data);


$string = 'Loren ipsum  ....';
$sender->add($sender);
```

Если нужно писать в разные логи, то slug нужного лога можно передавать опциональным параметром:


```php
use fastlogs\sdk\Sender;

$sender = new Sender();

$data = [123, 456, 'sldfkjsf'];
$sender->add($data, '23402493202');
```
