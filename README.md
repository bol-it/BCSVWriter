<p align="center">
  <h3 align="center">BCSVWriter</h3>

  <p align="center">
    BCSVWriter - библиотека для записи в csv файл.
    <br/>
    <br/>
  </p>
</p>

![Downloads](https://img.shields.io/github/downloads/bol-it/BCSVWriter/total) ![Contributors](https://img.shields.io/github/contributors/bol-it/BCSVWriter?color=dark-green) ![Issues](https://img.shields.io/github/issues/bol-it/BCSVWriter) ![License](https://img.shields.io/github/license/bol-it/BCSVWriter) 

### Подключение

1. Скопировать файл BCSVWriter.php в каталог App\Libraries
2. Прописать в контроллере:
```php
use App\Libraries\BCSVWriter;
```
## Использование

Создаем новый объект
```php
$csv = new BCSVWriter();
```
Задаем заголовок:
```php
$headers = ["id" => "№ п/п", "prim" => "Примечание"];
```
Установка заголовка
```php
$csv->setHeader($headers);
```
Отключение проверки длины массива
```php
$csv->setArrayCheckOfLength('false');
```
Задаем данные для записи в файл. Например:
```php
$items = ["id" => 1, "" => "prim" => "Тест"];
```
Добавление данных
```php
$csv->add($items);
```
Установка имени файла
```php
$csv->set_name("Test.csv");
```
Задаем путь для сохранения файла
```php
$path = storage_path('app/public/test/');
```
Сохранение файла в указанный каталог
```php
$csv->save_to_path($path);
```
Отправка на скачивание файла
```php
$csv->download();
```
