# PHP 7: Кратко про основные моменты.

Telegram: [@piratestories](https://t.me/piratestories)
| [Гайд](https://github.com/kakoi-to-pirat/web-developer-on-linux/blob/master/README.md) | [Книги](https://github.com/kakoi-to-pirat/web-developer-on-linux/blob/master/books.md) | [Статьи, доклады, ресурсы](https://github.com/kakoi-to-pirat/web-developer-on-linux/blob/master/reports.md) |

Быстродействие в новых версиях стало самым крутым и обсуждаемым нововведением. Теперь не нужно заморачиваться по оптимизации каких-то участков кода, а сразу писать понятный и поддерживаемый код. Далее на примерах я покажу, что мне понравилось в новых версиях:

## Замена тернарного оператора

На замену тернарного оператора пришёл «оператор объединения с null» или «null-коалесцентный оператор». Через два знака вопроса (??) можно указать цепочку значений в одну строку и будет выбрано первое значение, которое не равно null. PHP 5.6  
$test = isset($foo) ? $foo : null; PHP 7+  
$test = $foo ?? null;

## Групповое объявление классов, констант и функций

PHP 5.6  
use App\Bundle\Foo; use App\Bundle\Bar; use App\Bundle\Baz as B; PHP 7+  
use App\Bundle\{Foo, Bar, Baz as B};

## Декларация типов и возвращаемых значений

Теперь при объявлении метода для каждой переменной можно указать свой тип, а также тип данных, который вернёт этот метод. В PHP 7.0 доступны следующие типы: array, callable, bool, float, int, string, имя класса или интерфейса. В версии 7.1 добавили ещё void и iterable.  
function bar (int $a, float $b, string $c) : int { }

## Строгая типизация

Включили строгую типизацию  
declare(strict_types=1);

## Обработка ошибок и исключений

В PHP 7.0 появился новый класс для внутренних ошибок Error и интерфейс исключений Throwable. Теперь Error и старый класс Excetion реализуют Throwable (пользовательские классы не могут реализовывать данный интерфейс). Exception можно использовать для отлова исключений, которые будут обработаны и выполнение программы продолжится. Класс Error служит для необратимых исключений и выбрасывается в случае ошибки PHP или на уровне ошибок разработчиков. 

* [Подробнее про PHP 7](habrahabr.ru/post/280071/) 
* [Подробнее про PHP 7.1](habrahabr.ru/post/309858/) 
* [Подробнее про PHP 7.2](habrahabr.ru/company/avito/blog/335584/) 

Источник — [denisyuk.by](denisyuk.by/all/putevoditel-po-novovvedeniyam-php7)  
Первоисточник — [github.com/php/php-src/blob/php-7.0.0RC1/UPGRADING](github.com/php/php-src/blob/php-7.0.0RC1/UPGRADING)
