---
layout: page
title: Sprint Goals
description: Sprint Goals
theme: purple
---

Sprint goals: for each sprint, set one SMART goal to cover each of:
* professional practices (e.g. teamwork, client communication, ethical considerations),
* technical proficiency (e.g. framework challenges, ops challenges, source code control),
* Agile-ness (e.g. user stories, sprint management, scrum master).
At the end of the sprint, provide evidence that you have met each goal. Warning! Do not set goals you can’t achieve!
Your portfolio will need to demonstrate sufficient commitment to making appropriate professional, technical and methodological contributions to the project via evidence of achieving specific, measurable, appropriate, relevant and time-bound goals for each sprint (i.e. SMART goals)


## Sprint 1
### Professional practices
I communicated with my team members well, we have Facebook Messager and alos use GitHub project tools. The only problems was I didn't considered talk to our customer in the start of Sprint 1.
### Technical proficiency
In that time, the technical thing is Laravel framework stuff. I learnd a lot about MVC conception, and how to create Model, view, Controller under the Laravel framework.
**MVC** is acronmy of Model, View, Controller which represent the new design pattern in Web development industry. And Laravel framework is one of PHP framework can go quickly create MVC application.<br>
We use 
### Agile-ness
In the first Sprint, our team set up a goals which are finish four User stories below:
* Add new equipment
* Delete Item
* Edit Item
* Tracking Equipment


## Sprint 2
### Professional practices
### Technical proficiency
In this Sprint, when I done all new features and deploy on server, a error display below:
```bash
Migrating: 2019_04_10_040233_create_trackings_table

   Illuminate\Database\QueryException  : SQLSTATE[42S01]: Base table or view already exists: 1050 Table 'trackings' already exists (SQL: create table `trackings` (`id` int unsigned not null auto_increment primary key, `productID` int not null, `location` varchar(191) not null, `person` varchar(191) not null, `amount` varchar(191) not null, `dateMoved` varchar(191) not null, `created_at` timestamp null, `updated_at` timestamp null) default character set utf8mb4 collate 'utf8mb4_unicode_ci')

  at /home/se19s1_02/public_html/inventory-tracker-wecantthinkofaname/stocks/vendor/laravel/framework/src/Illuminate/Database/Connection.php:664
    660|         // If an exception occurs when attempting to run a query, we'll format the error
    661|         // message to include the bindings with SQL, which will make this exception a
    662|         // lot more helpful to the developer instead of just the database's errors.
    663|         catch (Exception $e) {
  > 664|             throw new QueryException(
    665|                 $query, $this->prepareBindings($bindings), $e
    666|             );
    667|         }
    668|

  Exception trace:

  1   PDOException::("SQLSTATE[42S01]: Base table or view already exists: 1050 Table 'trackings' already exists")
      /home/se19s1_02/public_html/inventory-tracker-wecantthinkofaname/stocks/vendor/laravel/framework/src/Illuminate/Database/Connection.php:458

  2   PDOStatement::execute()
      /home/se19s1_02/public_html/inventory-tracker-wecantthinkofaname/stocks/vendor/laravel/framework/src/Illuminate/Database/Connection.php:458

  Please use the argument -v to see more details.
```
The reason was database has already exist the table(Model), the solution like below:
```sql
php artisan tinker
Schema::drop('trackings')
```

### Agile-ness

## Sprint 3
### Professional practices
### Technical proficiency
### Agile-ness

## Sprint 4
### Professional practices
### Technical proficiency
### Agile-ness
