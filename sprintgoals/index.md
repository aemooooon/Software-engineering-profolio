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
I communicated with my team members well, we created Facebook Messager and also use GitHub project tools. The only problems was I didn't considered talk to our customer in the beginning of Sprint 1.
### Technical proficiency
In that time, the technical thing is Laravel framework stuff. I learnd a lot about MVC conception, and how to create Model, view, Controller under the Laravel framework.
**MVC** is acronym of Model, View, Controller which represent the new design pattern in Web development industry. And Laravel framework is one of PHP framework can go quickly create MVC application.<br>
We use MAMP stack to run our web application, and also use composer to manage php Laravel dependencies. So in OP room computer, I need install composer and direct to the php.exe everytime, because these computers does have recover function  when them restart. The only prepare things I need do each time:<br>
* Edit the .env file about database connection configuration to local MAMP database.
* Point webserver to our stocks public folder in the preferences of MAMP stack.

Install Laravel commandline:
> composer create-project --prefer-dist laravel/laravel stocks

Migrates commandline:
> php artisan migrate

Create a Model commandline:
> php artisan make:model ModelName -m

In the create_shares_table.php file, I can define model structure just like below:
```php
public function up()
    {
        Schema::create('modelnames', function (Blueprint $table) {
            $table->increments('id');
            $table->string('modelnames_name');
            $table->integer('modelnames_price');
            $table->integer('modelnames_qty');
            $table->timestamps();
        });
    }
```
then I can add the fillable property inside ModelName.php file
```php
namespace App;

use Illuminate\Database\Eloquent\Model;

class ModelName extends Model
{
  protected $fillable = [
    'modelname_name',
    'modelname_price',
    'modelname_qty'
  ];
}
```
Create controller
> php artisan make:controller ModelNameController --resource

Add controller to web.php
```php
Route::get('/', function () {
    return view('welcome');
});

Route::resource('modelnames', 'ModelNameController');
```

List route
> php artisan route:list


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
Today(2019-04-30) we have a meeting with our customer Paul and also we have greeting with our team members.
(Picture by Yandong here)
We have show all Sprint 3 working to Paul, and talk about some features need to update and some new features we need to catch up. I list the user stories below:
* customer want to Dashboard functionility on home page, just show some brief information like how many stocks do they have and how many equipment ouf of a number.
* Customer want to the system has authority functionility rather than every one else can access the page do any changing.
* Customer want to know how long the tracking equipment has been taken whcih is borrow time and return time needed.
* In tracking page, Customer wish see the borrow button instead of edit button.
* In tracking page, Customer likes to search item, makes his working more easy.
So all of ablow requirements are this Sprint golas. I made the all of stuff to User stories and put it into Kanban borad, make sure each of our team members can take it.

### Technical proficiency
About add search features to our project, I was considering three way to implement it.
1. Add a new controller named SearchController, put search form on my view pages such as list of trackings. When user type keyword to the form and click Search button, the SearchController will grab the data to its view page.
2. No more additional page to add, put search from on trackings page and grab data on trackings controller  and show query result still on view page which is trackings list page.
3. It's similar method 2, the only different is when user click the button without page refresh instead of use AJAX to interact back end controller.

I was try to use the first one, but some werid problems I haven't solve and also talk to Martin the best way is the second one as he said. So here I just list some key point:

### Agile-ness
As the decision of meeting, I have took two user stories in this stage, the one is Search features, other one is DeployOntoServer. And also I will do some change on trickings view such as dropdown list on the add new tracks page.<br>
The index route of trackingsController below, just check the user whether click the button or not, and return the both way might be result.
```php\
use Illuminate\Http\Request;
use Illuminate\Validation\Rule;
use App\trackings;
use DB;
use App\Inventory;

public function index(Request $request)
    {
        $k=$request->input('k');
        
        if($k==""){
            $trackings = trackings::all();
        }
        else{
            $trackings = trackings::where('location','LIKE','%'.$k.'%')->orWhere('person','LIKE','%'.$k.'%')->get();
        }
        
        // Here we need check if the query result is empty, how show message to view page??? 2019-05-02 by aemooooon
        // if(!count($trackings)){
        //     return view ('trackings.index')->withMessage('No Details found. Try to search again !');
        // }
		return view('trackings.index',compact('trackings'));
    }
```

Form tags in view of trackings:
```php
<form action="{{url('/trackings')}}" method="GET">
    <div class="input-group">
        <input type="text" class="form-control" name="k" placeholder="Search item"> 
            <button type="submit" class="btn btn-primary">Search</button>
    </div>
</form>
```
