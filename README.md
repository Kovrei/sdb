# Домашнее задание к занятию «Базы данных, их типы». Андрей Осипенков.

## Задание 1. СУБД
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

Приведите ответ в свободной форме.

### Ответ
**1.1. СУБД Ключ-значение. Предполагает четкость и простоту структуры, а также использование кэширования памяти. * Memcached, Redis**
**1.1. * Реализация разумных стратегий кэширования обеспечивает временное хранение часто используемых данных, таким образом уменьшая задержку за счет уменьшения избыточной обработки и получения данных. Могут использоваться различные методы кэширования, такие как краевое кэширование, которое обеспечивается сетями доставки содержимого (CDN), кэширование на стороне сервера или кэширование браузера. Чтобы оптимизировать эффективность кэша, выберите политику срока действия кэша и алгоритмы извлечения кэша, которые помогут обеспечить свежесть данных и использовать кэш.**

**1.2. СУБД Реляционная. 
1.2. * Oracle - компания специализируется на выпуске систем управления базами данных, связующего программного обеспечения и бизнес-приложений (ERP- и CRM-систем, специализированных отраслевых приложений).**

**1.3. СУБД Документно-оринетированная. 
1.3. * Поставленная задача является аналогичной 1.2 , т.к. имеет структурность значений и имеет гибкость. PostgreSQL**

**1.4 СУБД Графовые. 
1.4. * Для отдела закупок лучше использовать отдельную СУБД ООП (объектно-ориентированное программирование) с целью объединения СУБД логистов и закупок.**

**1.5. * СУБД ООП (объектно-ориентированное программирование). Postgres - объектно-реляционная субд, поэтому обладает широким функционалом, отлично интегрируется, много настроек, легко масштабируется, также имеет огромное комьюнити и большое количество специалистов для поддержки.**

## Задание 2. Транзакции
2.1. Пользователь пополняет баланс счёта телефона, распишите пошагово, какие действия должны произойти для того, чтобы транзакция завершилась успешно. Ориентируйтесь на шесть действий.

2.1.* Какие действия должны произойти, если пополнение счёта телефона происходило бы через автоплатёж?

Приведите ответ в свободной форме.

### Ответ

**2.1 Выбор оператора - ввод номера телефона - подтверждение данных - оплата счета - подтверждение оплаты - пополнение баланса - оповещение номера**
**2.1. * запрос оператора на настроенную дату и время - номер счета телефона - выбор банка для списания денежных средств - сумма сденежных средств - перевод денежных средств оператору - подтверждение банка - оповещение номера держателя карты списания - подтверждение опрератора - оповещение абонента**

## Задание 3. SQL vs NoSQL

3.1. Напишите пять преимуществ SQL-систем по отношению к NoSQL.

3.1.* Какие, на ваш взгляд, преимущества у NewSQL систем перед SQL и NoSQL.

Приведите ответ в свободной форме.

### Ответ

**3.1.:**
**5 преимуществ:**  
**1. Простота установки ограничений на доступ к данным для разных пользователей**  
**2. Применимость различных аутентификационных механизмов для обеспечения безопасности данных**  
**3. Лучше поддержка транзакционности ACID, что позволяет автоматически откатывать изменения при обнаружении проблемных транзакций и, таким образом, нивелировать возможные проблемы безопасности**  
**4. Мощный язык запросов, который позволяет обрабатывать сложные запросы**  
**5. Структурированность хронения данных**  

**3.1. * Основа NewSQL - это использование оперативной памяти и технологий быстрого хранения, таких как SSD, для обеспечения очень быстрой скорости доступа к данным и обработки транзакций. Объединение преимуществ SQL надежности и  преимуществ NoSQL гибкости и масштабированности. NewSQL предлагает решения, которые могут масштабироваться горизонтально, распределяя нагрузку по нескольким узлам.**

## Задание 4. Кластеры

Необходимо производить большое количество вычислений при работе с огромным количеством данных, под эту задачу выделено 1000 машин.

На основе какого критерия будете выбирать тип СУБД и какая модель распределённых вычислений здесь справится лучше всего и почему?

Приведите ответ в свободной форме.

### Ответ

**Основной тип критерия для данной задачи масштабируемость, гибкостить и производетельность. Модель NoSQL отвечает запросу. СУБД coloumn - oriented имеет функционал выполнения сложных аналитических запросов на больших объемах, и легкое, практически мгновенное, изменение структуры таблиц с данными, плюс существенная компрессия и сжатие, которое позволяет значительно экономить место. Если конкретизировать, можно посмотреть в сторону open-source колоночной СУБД ClickHouse. Также есть GreenPlum с mpp-архитектурой (массиво-параллельной) на основе Postgres, но GP подойдет не для всяких объёмов данных.**


