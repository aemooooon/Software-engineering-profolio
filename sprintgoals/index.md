---
layout: page
title: Sprint Goals
description: Sprint Goals
theme: purple
---

<hr>

## Introduction
Hello world!

<hr>

## Sprint 1
### Professional practices
I communicated with my team members well, everyone happy to join together as a team, we created Facebook Messager and also use GitHub project tools. The only problems were I didn't realize that we should talk to our customer at the beginning of Sprint 1(the picture below took by after we start the Sprint 1). To be honest I do not even know what exactly the Sprint was in this stage.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/groupmembers.jpg?raw=true" alt="group meeting with customer first time" style="margin: 20px;" />
### Technical proficiency
In that time, the technical thing is Laravel framework stuff. I learnd a lot about MVC conception, and how to create Model, view, Controller under the Laravel framework.
**MVC** is acronym of Model, View, Controller which represent the new design pattern in Web development industry. And Laravel framework is one of PHP framework can go quickly create MVC application.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190227_164259.jpg?raw=true" alt="what the MVC is" style="margin: 20px;" /><br>
We use MAMP stack to run our web application, and also use composer to manage php Laravel dependencies. So on our class room computer, I need install composer and direct to the php.exe each time, because these computers does have restore functionility  when they restart. The only prepare things I need do each time:<br>
* Make sure the .env file about database connection configuration to local MAMP database.
* Point webserver to our stocks public folder in the preferences of MAMP stack or run `php artisan serve`

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

#### INITIAL GOAL
> In the first Sprint, our team set up a goals which are finish four User stories below:
* Add new equipment
* Delete Item
* Edit Item
* Tracking Equipment

#### S
> Rob has described the basic project requirements on the class, and our team according to our current knowledge decide set up the above goals. Since all of us do not familiar Laravel, so we are going to make this together on room 201.

#### M
> That is a basic CRUD working on equipment model. we need at least four pages to show equipment list, could be adding new equipment, delete a exists equipment, could be updated a exists equipment. Also, hopefully do equipment tracking features.

#### A
> I have done web1, web2 in Otago Polyte, and also I had a couple of years experience on web development even that was old web development technology. Not to mention this time our team will work together, so I am confident I can achieve these goals. Also that will be our first milestone.

#### R
> Rob has mentioned the keywords of this project is inventory tracking. So all of the above goals are core functionality. its be must do.

#### T
> In terms of Time-Bound, this is a two-week period of the Sprint which means we will complete these task within two weeks. But I considered we should do that as soon as possible, because there are some unpredictable things that always happen, we must leave our own time to deal with it.


<hr>

## Sprint 2
### Professional practices
In this Sprint 2, I still communicate as always to my team members. Since I am poor English skills so I always keep the motivation to this area just make sure I am not missing anything I need to know to do. And this time I summed up the Sprint 1, I(we) first communicated deeply with our customers who Paul, expressed our thoughts, and listened to Paul's ideas and requirements. This meeting greatly simplified the complexity of the User stories, let our goals become clearer.<br>
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

#### INITIAL GOAL
> In the second Sprint, our team set up a goals which are finish five User stories below:
* More Indepth Items Descriptions
* Display
* Tracking Equipment(Its left over from the first Sprint)
* DeployOntoServer
* Raw numbers of stock

#### S
> Based on the work we completed last Sprint and from our customer Paus's requirements. We should keep the projected increment, in this stage, we still working together in the common room after hours.

#### M
> we will make the main page to display all exists equipment, also could click to view each specific equipment detail. In the final will deploy the app to the MariaDB server, just to show our customers the work of each stage, hopefully the wonderful experience be given.

#### A
> I can do this job alone, but for the average division of labor, I decided to do it together because the task is not particularly heavy.

#### R
> The core features are display equipment information. And deploy to server is our team work. Lecuter has been show us the tutorial which is how to deploy.

#### T
> In terms of Time-Bound, this is still a two-week period of the Sprint which means we will complete these task within two weeks.

<hr>

## Sprint 3
### Professional practices
In the beginning of Sprint 3, I took a meeting with some of the team members, also to our customer Paul. even though not everyone turns up. Clients Paul affirmed and encouraged our work in the previous stage and pointed out some details that need to be updated. I found our database struck get some problems and could not implements our equipment tracking especial on amounts. So we finally decided that is our working for now.<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190403_164159.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0404-1.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190404_132637.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0404-2.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/IMG_20190403_164212.jpg?raw=true" alt="Sprint 3 meeting" style="margin: 20px;" /><br>


### Technical proficiency
#### About conflicts
In normally, when we done a new features, we usually create a pull request on GitHub and wait the group someone else to merge it. But there is a very special situation which is some unknown reason we can not do that. we can not use online tools to merge, system said that "This branch has conflicts that must be resolved", but the Resolve conflicts button is not available just like picture below:<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/conflict.jpg?raw=true" alt="conflicts" style="margin: 20px;" />

In that time, we need use GitHub commandline tools which is GitBash, the solution just like this(make sure under the SSH connection):<br>
Step 1: From your project repository, bring in the changes and test.
```bash
git fetch origin
git checkout -b RetainInput origin/RetainInput
git merge master
```

Step 2: Merge the changes and update on GitHub.
```bash
git checkout master
git merge --no-ff RetainInput
git push origin master
```

then we will get the source code file wiht some <<<<<<<<<< code >>>>>>>>>>>>>>>>>> blocks. And that might be two group members take a sit together and merge new features by manually.
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/merge1.jpg?raw=true" alt="merge" style="margin: 20px;" />
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/merge2.jpg?raw=true" alt="merge" style="margin: 20px;" />

### Agile-ness

#### INITIAL GOAL
> In this stage, I will make changing about ERD module. (update)This time we encountered an unforeseen problem, that is the merger conflict occurred, unable to request the merger on GitHub online tools. But finally, we solved the problem with the help of the Lecturer Elise.

#### S
> As I mentioned before, the one of the user story is equipment tracking, and the key point is amounts. There is some number I put it to the database, but some other number I need to calculate by programming code. For example, there is 100 number of keyboard get to inventory stocks, I put the 100 as a field to the database one of the table. If someone borrows out 10 number of them. I will add a record to the tracking table, at the same time, I will do a calculation to update inventory stocks table amounts.

#### M
> That working just like change our model structure, its easier than create all-new model, but need be careful because change model is another way different to add a new one.

#### A
> I need to change the data structure as my part of work. At the same time, keep in time communication with the team member.

#### R
> Adjust the data model make sure the equipment could be tracked at any time, any place and who is utilizing.

#### T
> In this particular time, I want to spend no more one week to do this part, because I want to make some flexiable time to considering some other problems such as merge conflict solution.

<hr>

## Sprint 4
### Professional practices
Today(2019-04-30) we have a meeting with our customer Paul and also we have greeting with our team members.
(Picture by Yandong here)
We have show all Sprint 3 working to Paul, and talk about some features need to update and some new features we need to catch up. I list the user stories below:
* Customer want to Dashboard functionility on home page, just show some brief information like how many stocks do they have and how many equipment ouf of a number.
* Customer want to the system has authority functionility rather than every one else can access the page do any changing.
* Customer want to know how long the tracking equipment has been taken whcih is borrow time and return time needed.
* In tracking page, Customer wish see the borrow button instead of edit button.
* In tracking page, Customer likes to search item, makes his working more easy.
So all of ablow requirements are this Sprint golas. I made the all of stuff to User stories and put it into Kanban borad, make sure each of our team members can take it.<br>

<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0430-1.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0430-2.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>

At the middle of Sprint 4, We've made meeting second time with customer Paul and each other.<br>

<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0509-1.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0509-2.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0509-4.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>


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

HTTP Testing
1. Make a new HTTP Test `php artisan make:test HTTPTest`
2. A sample of code(HTTPTest.php, web.php)

```php

<?php

namespace Tests\Feature;

use Tests\TestCase;
use Illuminate\Foundation\Testing\WithFaker;
use Illuminate\Foundation\Testing\RefreshDatabase;

class HTTPTest extends TestCase
{
    /**
     * A basic feature test example.
     *
     * @return void
     */
    public function testExample()
    {
        $response = $this->get('/getdata');
        $response->assertJson(['Group'=>'Wecantthinkofaname']);
    }

    public function testView()
    {
      $response = $this->get('/');

      $response->assertViewIs('index.index');
    }

    public function testStatusCode()
    {
      $response = $this->get('/trackings');

      $response->assertStatus(200);
    }
}


Route::get('/getdata', function(){
    return response()->json(['Group'=>'Wecantthinkofaname']);
  });
```
3. Run teh test command
```bash
.vendor/bin/phpunit
or
phpunit
```


### Agile-ness

#### INITIAL GOAL
> The user stories and task from Kanban board:
<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/0510-2.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>

* Dropdown list (as a user I want the system easy to use, like when I add new tracking, I can just click dropdown list to choose my option value rather than type them.)
* Search (As a lecturer i want to be able to search through application to see the status of items and what is available.)


#### S
> Customer Paul said that they want to a search feature because there are so many items that could not show all of them on one page. And also in some operation interface would be easy such as navigation, HTML form elements Drop down list.

#### M
> I would do some change in our project. One thing is when customers add new item especially tracking detail, then can via drop down list to choose item model, borrower location and stakeholder name. Another thing is to add search form to our tracking page, make sure customers can quickly find the equipment they want.

#### A
> I would use the Bootstrap CSS framework to make sure all GUI looks better. And I will learn how to make multiple tables join together in Laravel, as well as the search result from multiple tables by the query. It involves how to transfer multiple data sets from the Controller to the View.

#### R
> These requirements are the basic requirements of the customer and the work assigned only to me. For a real product, this is also very important, very basic functionality. So no matter what, it must be done through study and research.

#### T
> This time the task is the most tangible content since the beginning of the project. It is a challenge for me. At the same time, other members of the team work with me on the same controller and view files, so there may be many contradictions and conflicts. 
I want to be able to complete the task within two weeks of this Sprint. To maintain real-time communication with other members, if struggling on anything, or any progress, I should to communicate with the customer, so as not to take a detour.

<hr>

## Sprint 5
### Professional practices
In the beginning of this Sprint 5, also might be the last Sprint, but I haven't made well. I had planned to meet with our customer Paul this afternoon, and Stephen had already made an appointment by mail yesterday. But today the weather is particularly bad, the wind is getting more rain, I can't get on time since I catch a cold with a fever. Communicating through our Messager, it seems that most people can't participate. This is a very bad start. In principle, I should not be able to meet with customers because of my fault. I am so sorry to everyone.
<br>
<img src="https://github.com/SoftEnOP/soften-portfolio-aemooooon/blob/master/assets/img/Messager.jpg?raw=true" alt="Sprint 2 meeting" style="margin: 20px;" /><br>

### Technical proficiency
In this Sprint, Martin and Elise tech us about Security and UX. And the Security wiht a example:
```php
What potential problems you see in the following code (there are at least three...):

$uname=$_POST['uname'];
$passwrd=$_POST['passwrd'];
$query="select username, password from users where username='$uname' limit 0,1";
$result=mysql_query($query);
$row = mysql_fetch_row($result);
if($row['password'] == $password) {... /* login successful */ ...}
```

I sumary the my opinion below.
1. Firstly, the variable accept from front end Form do not filter the script tag.
2. The SQL query statement do not use prepared statements.
3. The password has not been encrypt using any encryption method. <br />
In addition, there are a couple of problems such as not use try catch statement and not check the how many query result record the database have...

So I think the main risk is about SQL Injection. It is the placement of malicious code in SQL statements, via web page input. So our project based on MySQL database, and also has a lot place that user input. So firstly we need considering about SQL Injection risk. When any User input think about use GET or POST way to send or request. And all SQL query statement use PHP prepared statement to filter invalid keywords relative the malicious code such the condition like `"or""=", or 1=1` or after the SELECT statement colon follow `;DROP TABLE inventories`. So these kinds of Injection will bring very serious consequences. Of course there have other way to avoid these attack in many different WEB technology.

In terms of UX, I feel like that is really important things.

> “No product is an island. A product is more than the product. It is a cohesive, integrated set of experiences. Think through all of the stages of a product or service – from initial intentions through final reflections, from first usage to help, service, and maintenance. Make them all work together seamlessly.” <br /><br />
— Don Norman, inventor of the term “User Experience”

So basicaly we create and develop a Application that not only make a app the user just use it. We also need think about how about the user experience, how easy, convenient to use and  how much good feeling the user could get.

In our project, we did some thing about that even though not perfact. We used the Form validation which is support by Laravel framework, but also I did some research about other not default rules. for example, I have changed how validate Dropdown list element:
```php
use Illuminate\Validation\Rule;
$request->validate([
            'productID'=>['required',Rule::notIn(['0']),],
            'location'=> ['required',Rule::notIn(['0']),],
            'person' => ['required',Rule::notIn(['0']),],
            'amount' => 'required',
            'borrowdate' => 'required',
            'returndate' => 'required'
               ]); 
```
like productID, location and person field all from Dropdown List.

meanwhile, we keep the old already input data by user, use old method by Laravel. `<input type="text" class="form-control" name="name"  value="{{ old('name') }}"/>`. There are other many way to implement UX, not only from technical, but also I could from design to considering. I found this area is very intersting, Coincidentally, Otago Polytechnic is about to run this Paper, I really want to take this paper, but maybe there will never be a chance.


### Agile-ness
To be honest, during this time, I did not use the SMART template to set my detailed goals. 
Because I got sick for a few days, then my team didn't assign me a lot of tasks, just modify the information about the stocks table. 

Then I did some optimization and improvement in terms of security and user experience. 
But at the same time, let me understand why the Agile Manifesto said on the first day that everything should be people-centered, and no documents or processes are important. 
If someone is ill, or if they can't work for any other reason, everything doesn't make sense.
