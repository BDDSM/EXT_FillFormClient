# Расширение ЗаполнениеФормыКлиент
Расширение для БСП. Позволяет подключать внешние обработки заполнения объектов без их записи на клиенте. 

## Использование

Добавьте расширение в конфигурацию в небезопасном режиме (расширение серверных методов не работает в безопасном режиме).

В СведенияОВнешнейОбработке() при описании команды:
  - ```Использование = "ЗаполнениеФормы"```
  - а в конце ```Идентификатор```a добавьте ```"НаКлиенте"``` или ```"Клиент"```.

Пример:
```
Команда.Использование = ДополнительныеОтчетыИОбработкиКлиентСервер.ТипКомандыЗаполнениеФормы(); // "ЗаполнениеФормы"
Команда.Идентификатор = "ЗаполнениеТоварамиПоставщикаНаКлиенте";
```

## Пояснения

Технически результат будет соответствовать ```Использование = "ВызовКлиентскогоМетода"``` без требования записи. Используйте ```ВладелецФормы``` для доступа к вызвавшей форме.

Именно так (через ЗаполнениеФормы) сделано из-за легаси: в таком виде адаптированные обработки не будут работать при подключении их без расширения, а уже существующие не начнут работать по другому.

## Вопросы

Через [issues](https://github.com/klimenko-1c/EXT_FillFormClient/issues), плиз.

## Струкутра репозитория

 - в bin/ - собранные расширения
 - в src/ - исходники
 - в ext/ - прочие 

## Прочее
Использовано при сборке:
 - Платформа 8.3.10.2639
 - БСП 2.4.4.120