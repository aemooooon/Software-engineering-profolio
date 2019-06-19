---
layout: page
title: Personal reflection
description: Personal reflection
theme: red
---

# Sprint 1
> #### What did you do well?

At the first of Sprint, my communication with my team members was very smooth, and we are all very happy to be in a team. 
I talked a lot about each other. Everyone feels particularly energetic, we get hundred of power, hundred of motivation to waiting to do something big.

> #### What could you have done better?

If I want to say that there is something I can improve or say to be more perfect, it is that we did not realize the communication with the customer at the beginning. Since I have not yet read the agile manifesto and principal deeply, it is only halfway through the first Sprint that we not only have to communicate well with each other but also communicate with our customer Paul more importantly. So the problem is that we didn't meet the customer for the first time and extract his ideas.

> #### What lessons did you learn?

At this stage, I learned the basics of the Laravel framework and reviewed the use of GitHub. I just finished web 2 PHP paper last semester, but I don't know anything about the Laravel framework. Fortunately, I have a little understanding of the MVC pattern, so when Martin instills the MVC concept on the whiteboard, I was relieved because I probably know what Laravel is all about, and this week I learned about Laravel's basic additions, deletions, and changes, how to create models, controllers, and views, and let them work. In addition, we have learned how to use GitHub in professional practice paper, and we are constantly using it in the after one year. But that is the most basic. Now we need to understand more deeply, such as the use of branches, the resolution of conflicts, and the focus on the process of multi-person team collaboration development. 
Elise said, try not to delete anything, including branches, commit records, etc., as far as possible, we solve the problem directly, leaving all the final records. I think this is also a good way to make sure that we have really learned this skill so that we can use and collaborate correctly in the workgroup in the future. What's interesting is that I made the first commit in the GitHub class and the Elise sent me a lovely card. This is a happy thing...

> #### What barriers did you encounter?

For me, the first barrier is the difference in philosophy in the first Sprint. I have had a couple of years of development experience, probably a decade ago, so I may have some traditional development methods living in my brain such as waterfall development. When Rob first told us about the project topic and basic needs, what I thought in my mind was the whole prototype of the project. I built a structure of Inventory tracker in my subconscious, and I hope to implement it in the first Sprint. 

Another reason why there may be more functions is that we don't listen to customers' ideas, so I may think a little more. 
But when I was talking to my team members, especially Jorden, in particular, made different ideas. 
That's the module that we only complete a small number of independent functions at each Sprint. We don't make goals that we can't accomplish. This is called Agile development. After my careful consideration, in addition to the above reasons, I think my poor English skills are also a barrier placed in front of me.


# Sprint 2

> #### What did you do well?

In the second Sprint, the best I did was to communicate with the customer. This time, I learned the bad experience I did last time. At the beginning of the Sprint, I met with the client Paul. I first summarized the work of the previous Sprint and proposed our next goal. Paul also pointed to the above. Both of the above aspects have been asked and verified. To ensure that our customers and our team have a unified goal, we are working hard to achieve the goal within a specified time, without making a mistake. I personally think this time is perfect communication.

> #### What could you have done better?

I think what I can improve is that Laravel is not deep enough to learn, and there are some problems that are not thorough enough. Maybe it is because time is not particularly much. For example, when I was deploying, there was an error (I wrote it in Sprint 2 Golas) because "The base table or view already exists: 1050 Table Trackings already exists". And I just found a solution on the google, that is to delete the table directly, and then continue to deploy. The cost paid is that I lost the data I tested at the beginning. So for us at this stage, there is no problem. Because we don't have any valuable data at the moment.  But if not?  Then this method is not feasible. As Martin said, my xxx is sick, and my solution is to buy a new xxx directly, instead of trying to cure xxx. The problem is that Laravel does have a cure for this disease. Therefore, I feel that the next time I encounter a similar problem, I must thoroughly study the problem and solve the problem fundamentally.

> #### What lessons did you learn?

At this Sprint, I learned the Scrum and GitHub Agile workflows, learned more about using the Kanban feature, and all user story avatars were assigned to each of our team members. Then we will change our state through our work to know that the final completion is complete and then the work is finished. 

At the same time, because we have completed some basic functions in the first phase, we also learned how to deploy our current work to our public server. The main purpose of this is to let our customers see it in real time. Go to our results at each Sprint and make comments and suggestions as well as the task requirements they need to modify. Technically, deployment is not that difficult, because almost everyone has completed Linux and MariaDB learning.

> #### What barriers did you encounter?

The biggest obstacle for me is still English skills, although I am very familiar with the business logic of similar small systems, and I am very familiar with code and technology. But many times I can't understand what I should do for the first time through my hearing, what everyone needs. For example, when Rob finished the requirements in class, I didn't know what happened. Fortunately, Stephen wrote everything, and I understood what happened after reading. So this is my personal obstacle. 
Hey...

# Sprint 3

> #### What did you do well?

At Sprint 3, I have to say that communication is still the best part of what I do. Although at the beginning of the meeting with the customer, not everyone on the team was present, I still want the customer to report on the work of the previous Sprint, and get the recognition and encouragement from the customer, even though I use lame English. 

At the same time, when I showed the function to the customer, I found that our equipment did not get effect tracking, because our database model ERD has problems, different operators and different types of equipment cannot be tracked, we need to put the data entity divided into multiple tables to achieve this, but also in line with the third normalization of the database.

> #### What could you have done better?

I think that in this Sprint, I didn't do well enough to using GitHub completely. When Elise gave us the GitHub Guide card, I think these commands are very simple, because I know the specific meaning of these commands. But when it is actually used, there are still many problems. The first is that the use of habits and convention has not yet formed a potential awareness in my mind. 

For example, whenever I add a new feature, I didn't think of creating a new branch for the first time, but I was used to working directly on the master branch, so this habit is the first thing I need to correct. 

The other one is that I ignored some of the necessary processes, such as the Git pull command to get the latest version before any updates. So this leads to conflicts and contradictions when I complete my function and submit a code merge request. And these conflicts can't be solved online, we need to use the Git merge command to force the merge, and then manually compare the differences between the files to resolve conflicts and contradictions. 

At this time, if I am not familiar with the code of other team members, I need two people to solve together, which in some ways actually reduces the development efficiency, but also makes the code messy. So I need to gain more experience in this area to enrich and enhance my Git usage.

> #### What lessons did you learn?

In this Sprint, in addition to learning the knowledge of the Laravel framework and the use of GitHub, the most time spent on me is the model design of complex databases. Not to mention that this project is only a small project, but for the design of the database, there is a little bit tricky.  Although I have done the database foundation and the learning of database 2's paper, I have not encountered a complicated model structure at this school. 

In this example, we not only have equipment items, we also need to save the quantity of inventory, and no matter who borrows or returns the number, there are some calculations that we can't fully dynamic calculate in the program code, so this requires the design of the database. Need to be very flexible. It is neither redundant nor fulfills the requirements.

> #### What barriers did you encounter?

For me, there aren't too many technical challenges. But the obstacles still exist. For example, in this Sprint, I just worked very well in the first week. But in the coming period, due to the two weeks middle holiday, I spent too much time with my family and taking care of the children. So there is no one hundred percent to complete the assigned task. But I think this is also a no-brainer. After all, learning is not the whole of life. I can't do everything in perfection. I can only try to maintain this balance.

# Sprint 4

> #### What did you do well?

To be honest, this Sprint is the best I have done in all of Sprint, and I feel the most fulfilling. It is embodied in the following aspects: 
1. Good communication, I have met team members and have conducted in-depth communication with the customer a couple of times. 
2. Learn most of the new things and complete the most features. For details, please see “What lessons did you learn?”.
3. Time management is better than before. The time and tasks set in my SMART goal are completed on schedule.

> #### What could you have done better?

Nothing is perfect. 
In the same way, there is always more perfect than what I am currently doing. I need to work hard to pursue. 

But in this special period, I am very confident that I am doing very well at this stage. Relatively considering, the understanding of agile, the use of the Scrum process, the opportunity of teamwork, and the management of time have all been more I have a comprehensive understanding, so I want to say that I need to do better. I only need to follow my current motivation and habits and I will do better.

> #### What lessons did you learn?

In this process, I learned the most in Technical Proficiency, because I completed the entire search module and all the additions to the new items, all of the other tables associated with the use of Dropdown List to display. 
In fact, these two functions have a common feature, which is to provide a more convenient use process for the customer's operation.

I learned how to add a Form to the Laravel View, and at the same time, whether the search results and the interface are on the same page or separate the pages, I have done research in two different ways, and finally chose to implement on the same page. I need to determine if the user has entered any keywords, whether the search button has been clicked, and different actions will display different feedbacks and search results. The more difficult problem during this period is that my search result is the result of a correlation query from at least 3 tables. Some of them only store the ID field of the entity, so I need to associate the literal content of all fields in detail and then be friendly show them.

In addition, the same problem with the Dropdown List problem, I need to take the data from the Model, and then pass to the View through the controller, and finally through the template operation to bind multiple pieces of data into the HTML.  All of these things are relatively simple if implemented in PHP.  But this is done with Laravel, so it took some time to research and learn. But the ending result is good and there is a sense of victory. I am very happy.


> #### What barriers did you encounter?

Regarding the barriers, I think there are a few small barriers in personal styles.
I have already said that this time is my own feeling of the best, but also the smoothest of all the work. No matter whether it is communication with the customer, the team, or the control of the Scrum process, and whether or not to follow the agile manifesto and the agile principles, there is no big problem. At the same time, the efficiency of the entire team is relatively high. We basically all achieved the goals we set.

Although, there are some stuff I didn't make perfact. For instance, I should use AJAX to implement the Search features, When User type any letter or words, the results will automitcally changing by keywords. This will improve the User experience. But because I lack the motivation to pursue perfection, perhaps lazy or other reasons, I did not make this module as perfect as I imagined. So this is a shortcoming of my personal styles. I need to change my inertia, then change myself and pursue the perfection of the project.


# Sprint 5

> #### What did you do well?

In this Sprint, what I did better was to study a lot of knowledge about Web security and user experience. Rather than simply be limited the Web development technology. All previous learning and direction are to make the function of the project as good as possible, never considering the user experience and website security. Through the explanations of Matin and Elise, I found that these two aspects are especially important. Imagine if you do something beautiful and powerful if the security is not good, the user experience is poor, it will be worthless, there will be no customers. Willing to spend money to buy your products, let alone have any market competitiveness. 
So from the perspective of the whole career planning, we have to learn more. I am very happy. I understand these reasons, which opens up my vision of viewing a project from the whole. If I am a project leader, I will be in the project all these aspects are considered at the beginning. Such a product is called a real product. I should also continue to delve into research and study in these areas.


> #### What could you have done better?

In fact, there is a lot of work during this period that I should do, and it should be better. The most important one is about Items stock level which is user story As a System Admin I want to be notified when stock is low or critically low for specific items because I will need to order more. 

Since I am already working on stock, I should go one step further and do more to make this feature perfect. Because this is a very important function, our customers are responsible for managing the equipment, including the shortage of stock, and it takes more time to get new equipments. You can't say that I can finish the work in a short time. So we need our system to give users a quantitative warning.

> #### What lessons did you learn?

I am very interested in SQL injection, and I also learned a lot about the basic attack principle and protection principle of this topic. For example:
1. Get request method: http://www.example.com/products?category=keyborad <br />
Looking closely at this address, you will find that the request method is Get, so if you want to inject only need to change the URL address, to create fake condition or use SQL comment to attack. such as:
* http://www.example.com/products?category=keyborad'--
* http://www.example.com/products?category=keyborad or 1=1
2. POST requet method:<br />
* SELECT name,password FROM users WHERE *** ' UNION SELECT username,password FROM users--
just put these statement to form which is the user input

If you want to prevent others from attacking, we must first be familiar with these attacks. Different languages and frameworks have their own code and methods. What we have to do is to maintain a sense of alertness.

> #### What barriers did you encounter?

My barriers are still language barriers. Learning, research and reading all need to read a lot of documents. My language ability makes my learning speed and efficiency very slow. A lot of times I can understand the code, but I can't fully understand the text and sentences that describe the code. It feels like this is a very weird phenomenon. 

On the other hand, my illness and absence are also an obstacle for the project. You should find out the agile manifesto and principles. 
The first rule of the manifesto, the fourth, fifth, sixth, and eighth principles are people-based and core. If people can't participate in it, nothing can be done. So this is the importance of people in agile. For me in this Sprint, it is another barriers.


# All Sprint Timetable
* Sprint One(3.6-3.20)
* Sprint Two(3.20-4.3)
* Sprint Three(4.3-5.1)
* Sprint Four(5.1-5.15)
* Sprint Five(5.15-5.29)
