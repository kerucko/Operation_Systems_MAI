## Вариант 21

Реализовать распределенную систему по асинхронной обработке запросов. В данной распределенной системе должно существовать 2 вида узлов: «управляющий» и «вычислительный». Необходимо объединить данные узлы в соответствии с той топологией, которая определена вариантом. Связь между узлами необходимо осуществить при помощи технологии очередей сообщений. Также в данной системе необходимо предусмотреть проверку доступности узлов в соответствии с вариантом. При убийстве («kill -9») любого вычислительного узла система должна пытаться максимально сохранять свою работоспособность, а именно все дочерние узлы убитого узла могут стать недоступными, но родительские узлы должны сохранить свою работоспособность.


### Топология 2

Аналогично топологии 2, но узлы находятся в дереве общего вида.

### Набора команд 3 (локальный таймер)

Формат команды сохранения значения: exec id subcommand

```
subcommand – одна из трех команд: start, stop, time.
start – запустить таймер
stop – остановить таймер
time – показать время локального таймера в миллисекундах
```

 ### Команда проверки 3

Формат команды: heartbit time

Каждый узел начинает сообщать раз в time миллисекунд о том, что он работоспособен. Если от
узла нет сигнала в течении 4*time миллисекунд, то должна выводится пользователю строка:
```
«Heartbit: node id is unavailable now», где id – идентификатор недоступного вычислительного узла.
```