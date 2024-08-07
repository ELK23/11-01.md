# Домашнее задание к занятию "`Базы данных, их типы`" - `Ли Олег`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1 СУБД

`Кейс

Крупная строительная компания, которая также занимается проектированием и девелопментом, решила создать правильную архитектуру для работы с данными. Ниже представлены задачи, которые необходимо решить для каждой предметной области.

Какие типы СУБД, на ваш взгляд, лучше всего подойдут для решения этих задач и почему?

1.1. Бюджетирование проектов с дальнейшим формированием финансовых аналитических отчётов и прогнозирования рисков. СУБД должна гарантировать целостность и чёткую структуру данных.

1.1.* Хеширование стало занимать длительно время, какое API можно использовать для ускорения работы?

1.2. Под каждый девелоперский проект создаётся отдельный лендинг, и все данные по лидам стекаются в CRM к маркетологам и менеджерам по продажам. Какой тип СУБД лучше использовать для лендингов и для CRM? СУБД должны быть гибкими и быстрыми.

1.2.* Можно ли эту задачу закрыть одной СУБД? И если да, то какой именно СУБД и какой реализацией?

1.3. Отдел контроля качества решил создать базу по корпоративным нормам и правилам, обучающему материалу и так далее, сформированную согласно структуре компании. СУБД должна иметь простую и понятную структуру.

1.3.* Можно ли под эту задачу использовать уже существующую СУБД из задач выше и если да, то как лучше это реализовать?

1.4. Департамент логистики нуждается в решении задач по быстрому формированию маршрутов доставки материалов по объектам и распределению курьеров по маршрутам с доставкой документов. СУБД должна уметь быстро работать со связями.

1.4.* Можно ли к этой СУБД подключить отдел закупок или для них лучше сформировать свою СУБД в связке с СУБД логистов?

1.5.* Можно ли все перечисленные выше задачи решить, используя одну СУБД? Если да, то какую именно?

Приведите ответ в свободной форме.`

1.1 Реляционная база данных, у нее самые точные значения, и можно обеспечить высокую защиту данных

1.2. NoSQL документо ориентированную, потому что она имеет высокую производительность, и устойчивость к распаду, также она обладает целостностью, если эти данные будут просматриваться персоналом разных отделов, нужно, чтобы все имели один результат

Для crm лучше использовать реляционную бд, так как она имеет гибкость нужную для crm

1.2.* Реляционная бд может использоваться для обеих задач, но лучше разделить их физически, чтобы запросы в одну бд не тормозили запросы в другой бд

1.3. Реляционная база данных имеет самую простую и понятную структуру, также ее можно подстраивать под структуру компании

1.3.* Можно интегрировать ее в crm

1.4. Реляционная субд работает со связями, и может связать все требуемые значения

1.4* Лучше сделать отдельную СУБД, потому что у них разные цели, и данные, которые там будут хранится будут не связаны друг с другом

1.5* Реляционная бд может использованна для всех запросов



### Задание 2 Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Приведите ответ в свободной форме.


2.1. пользователь нажимает кнопку оплатить
      банк проверяет баланс счета в банке
      банк определяет счет оператора
      банк отправляет транзакцию на счет оператора
      оператор определяет данные по транзакции
      счет телефона поплняется

2.1.* у оператора есть согласие на автоплатеж
      оператор отправляет запрос в банк на автопополнение
      банк принимает и обрабатывает запрос
      банк проверяет баланс клиента
      банк дает добро на списание средств
      счет пополнен


---

### Задание 3  SQL vs NoSQL
3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Приведите ответ в свободной форме.

3.1. стандартизированная схема
      большее количество пользователей
      sql стандартный и простой язык
      ACID
      возможность настроить схему под большинство задач
      
3.1.* ACID
       SQL язык
       проще чем стандартный sql



### Задание 4  Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?
На основе качества данных которые будут использоваться, если известен тип данных, их связь и т д. можно использовать реляционную даннух с жесткой структурой, если данные безпорядочны, различны, и не известна их связь, нужно использовать noSQL
Здесь многоуровневая модель вычеслений подходит больше всего, если различные машины будут отвечать за обработку, хранение, контроль и мониторинг, то их работа будет намного стабильнее и производительность выше



```
