
# Домашнее задание к занятию "`Базы данных, их типы`" - `Яковлев Константин`

### Задание 1. `СУБД`

```
Кейс
Крупная строительная компания, которая также занимается проектированием и девелопментом, 
решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, 
которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?
```

```
1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. 
СУБД должна гарантировать целостность и чёткую структуру данных.

- реляционный тип т.к. этот тип СУБД гарантирует целостность и четкую структуру

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. 
Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

- реляционный тип, потому что этот тип СУБД может гарантировать быстроту и гибкость 

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, 
сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

- в этом случае на мой взгляд лучше использовать иерархическую модуль СУБД, потому что в ней можно легко составить
структуру 

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам 
и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

- здесь хорошо подойдёт REDIS т.к. в ней есть реализация кэширования

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?
```


### Задание 2. `Транзакции`

```
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, 
чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

- Прочесть баланс на счету карты
- Уменьшить баланс "сумму"
- Сохранить новый баланс счёта карты
- Прочесть баланс на телефоне 
- Увеличить баланс "сумму"
- Сохранить новый баланс телефона


2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

- прочесть календарь 
- Прочесть баланс на счету карты
- Уменьшить баланс "сумму"
- Сохранить новый баланс счёта карты
- Прочесть баланс на телефоне 
- Увеличить баланс "сумму"
- Сохранить новый баланс телефона
- создать пометку в календаре 
```


### Задание 3. `SQL vs NoSQL`

```
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

- Базы данных SQL масштабируются вертикально, а базы данных NoSQL масштабируются горизонтально.
- Базы данных SQL основаны на таблицах, в то время как базы данных NoSQL.
представляют собой хранилища документов, ключей-значений, графиков или широких столбцов
- Базы данных SQL используют язык структурированных запросов (SQL) и имеют предопределенную схему. 
Базы данных NoSQL имеют динамические схемы для неструктурированных данных.
- Базы данных SQL являются реляционными, а базы данных NoSQL — нереляционными.
- Базы данных SQL лучше подходят для многострочных транзакций, а NoSQL лучше подходит для неструктурированных данных, таких как документы или JSON.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

- Вертикальное + горизонтальное масштабирование
- поддержка и даже расширенный функционал для Old SQL
- Высокая эффективность при обработке сложных запросов и небольших запросов
```


### Задание 4. `Кластеры`


```
Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

- здесь необходимо использовать NoSQL систему, потому что нужна поддержка языков прогнозирования,
для того что бы програмистам не приходилось преобразовывать объекты в таблицы и строки со связями и обратно.
```
