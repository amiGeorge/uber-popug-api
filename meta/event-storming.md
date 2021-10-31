### Таскер

**Логин в таскер**

- Actor - User (any role)
- Command - Login to tasker
- Data - Auth data
- Event - User.LoggedInToTasker

**Создание задачи**

- Actor - User (any role)
- Command - Create task
- Data - user (employee role) + decription + status 
- Event - Task.Created

**Кнопка "заассайнить задачи"**

- Actor - User (role is manager or admin)
- Command - Assign tasks
- Data - ??? 
- Event - TasksAssigned (or a single event for all tasks?)


**Ассайн задачи на сотрудника**

- Actor - TasksAssigned or TaskFeesCalculated
- Command - Assign task
- Data - user, task public id

**Отметить задачу как вполененную**

- Actor - User (any role)
- Command - Mark task as completed
- Data - user, task public id
- Event - TaskCompleted

### Бухгалтерия

**Логин в бухгалтерию**

- Actor - User (any role)
- Command - Login to accounting
- Data - Auth data
- Event - User.LoggedInToAccounting

**Рассчитать цены задачи**

- Actor - Task.Created
- Command - Calculate task fees
- Data - task public id
- Event - TaskFeesCalculated

**Списать assigned fee со счета сотрудника**

- Actor - TaskFeesCalculated
- Command - Debit user account for task assigned fee
- Data - task public id, user public id
- Event - ???

**Начислить completed fee на счет сотрудника**

- Actor - TaskCompleted
- Command - Debit user account for task completed fee
- Data - task public id, user public id
- Event - ???


### Аналитика

**Посчитать сегодняшний профит компании за день**

- Actor - System scheduler
- Command - Calculate daily company profit
- Data - -
- Event - ???

**Посчитать кол-во сотрудников с негативным профитом**

- Actor - System scheduler
- Command - Calculate negative users with negative profit count
- Data - -
- Event - ???

**Посчитать самые профитные задачи для компании**
- Actor - System scheduler
- Command - Calculate most profitable tasks for 1 / 7 / 31 days
- Data - -
- Event - ???
