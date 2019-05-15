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
I communicated with my team members well, everyone happy to join together as a team, we created Facebook Messager and also use GitHub project tools. The only problems were I didn't realize that we should talk to our customer at the beginning of Sprint 1(the picture below took by after we start the Sprint 1). To be honest I do not even know what exactly the Sprint was in this stage.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/groupmembers.jpg?raw=true" alt="group meeting with customer first time" style="margin: 20px;" />
### Technical proficiency
In that time, the technical thing is Laravel framework stuff. I learnd a lot about MVC conception, and how to create Model, view, Controller under the Laravel framework.
**MVC** is acronym of Model, View, Controller which represent the new design pattern in Web development industry. And Laravel framework is one of PHP framework can go quickly create MVC application.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190227_164259.jpg?raw=true" alt="what the MVC is" style="margin: 20px;" /><br>
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

Create View
just put all view page under the resources folder:
```bash
resources
├── js
│   ├── app.js
│   ├── bootstrap.js
│   └── components
│       └── ExampleComponent.vue
├── lang
│   └── en
│       ├── auth.php
│       ├── pagination.php
│       ├── passwords.php
│       └── validation.php
├── sass
│   ├── app.scss
│   └── _variables.scss
└── views
    ├── css
    │   ├── bootstrap.css
    │   └── style.css
    ├── inventories
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   └── index.blade.php
    ├── layout.blade.php
    ├── locations
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   └── index.blade.php
    ├── people
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   └── index.blade.php
    ├── trackings
    │   ├── create.blade.php
    │   ├── edit.blade.php
    │   └── index.blade.php
    └── welcome.blade.php
```

### Agile-ness
In the first Sprint, our team set up a goals which are finish four User stories below:
* Add new equipment
* Delete Item
* Edit Item
* Tracking Equipment


## Sprint 2
### Professional practices
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0319-1.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0319-2.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
### Technical proficiency
We get a new user story from our customer Paul which is "As a system admin i want information entered into the application to be saved there once page has been refreshed.", it is interestingly that lecture Martin just tell us a solve way like below. I have talk to Stefi a lot of thing about that problem. but there was no reslut to figure out. So just keep record this here. I feel like that is a little bit special.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190410_164510.jpg?raw=true" alt="keep onl information" style="margin: 20px;" /><br>
In addtional, when I done all new features and deploy on server, a error display below:
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
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0404-1.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0404-2.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
### Technical proficiency
#### About conflicts
In normally, when we done a new features, we usually create a pull request on GitHub and wait the group someone else to merge it. But there is a very special situation which is some unknown reason we can not do that. we can not use online tools to merge, system said that "This branch has conflicts that must be resolved", but the Resolve conflicts button is not available just like picture below:
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/conflict.jpg?raw=true" alt="conflicts" style="margin: 20px;" />

In that time, we need use GitHub commandline tools which is GitBash, the command just like this:
```bash
git fetch origin
git pull origin master
git merge branchname
```
then we will get the source code file wiht some <<<<<<<<<< code >>>>>>>>>>>>>>>>>> blocks. And that might be two group members take a sit together and merge new features by manually.
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/merge1.jpg?raw=true" alt="merge" style="margin: 20px;" />
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/merge2.jpg?raw=true" alt="merge" style="margin: 20px;" />

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
So all of ablow requirements are this Sprint golas. I made the all of stuff to User stories and put it into Kanban borad, make sure each of our team members can take it.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0430-1.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0430-2.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
### Technical proficiency
About add search features to our project, I was considering three way to implement it.
1. Add a new controller named SearchController, put search form on my view pages such as list of trackings. When user type keyword to the form and click Search button, the SearchController will grab the data to its view page.
2. No more additional page to add, put search from on trackings page and grab data on trackings controller  and show query result still on view page which is trackings list page.
3. It's similar method 2, the only different is when user click the button without page refresh instead of use AJAX to interact back end controller.

I was try to use the first one, but some werid problems I haven't solve and also talk to Martin the best way is the second one as he said. So here I just list some key point:

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

return mutiple dataset/objects to view in controller
```php
    public function create()
    {
        $inventories=Inventory::all();
        $locations=Location::all();
        $pss=People::all();

        return view('trackings.create', compact('inventories', 'locations', 'pss'));
    }
```

validate dropdown list
```php
        $request->validate([
        'productID'=>[
            'required',
            Rule::notIn(['0']),
        ],
        'location'=> [
            'required',
            Rule::notIn(['0']),
        ],
        'person' => [
            'required',
            Rule::notIn(['0']),
        ],
		'amount' => 'required',
		'dateMoved' => 'required'
      ]); 
```

dropdown list in view
```html
       <div class="form-group">
          @csrf
          <label for="ProductID">Equipment:</label>
              <select class="form-control m-bot15" name="productID">
              <option value="0">Select Equipment</option>
                  @foreach($inventories as $inventory)
                      <option value="{{ $inventory->id }}">{{ $inventory->name }}</option>
                  @endforeach
              </select>
          </div>
```

### Agile-ness
As the decision of meeting, I have took two user stories in this stage, the one is Search features, other one is DeployOntoServer. And also I will do some change on trickings view such as dropdown list on the add new tracks page.<br>

