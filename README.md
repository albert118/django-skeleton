# django-skeleton

**A django project skeleton for easy setup on a LAMP server! Under development...**

##Some of the features currently built-in:

*Ready project skeleton for development.
*Logging/Debugging custom implemented.
*For Python 3.+
*Based on Django 1.8 project structure.
*Better Security with [12-Factor](http://12factor.net/) recommendations.
*Ready for a MySQL database!

## Setup:
Using [Django's](https://docs.djangoproject.com/en/2.1/ref/django-admin/) admin startproject function to fetch the code from this Git:
Note: by default the --template argument expects .py file types, use the --extension argument to also add README, html code and so forth to your project. Remove these if you don't want the README in your code (ideally you would though for completeness). 

1. `$ django-admin.py startproject --template=https://github.com/arocks/edge/archive/master.zip --extension=py,md,html,env my_proj`
*Change my_proj to whatever name you want! 
2. `$ cd my_proj`
*Now copy the sample local environment variables to a permanent one, makes it easier to go back in case of issues.
3. `$ cp my_proj/settings/local.sample.env my_proj/settings/local.env`
4. Setup a [MySQL server](http://www.ntu.edu.sg/home/ehchua/programming/sql/MySQL_HowTo.html#intro), see number 3. If you're new to MySQL or need a refersher then read the bits before.
5. Setup a user for Django to use when making migrations;
*Make sure a client is running before doing this!
`$ mysql -u root -p     *//Windows
`$ ./mysql -u root -p   *//Mac OS X
*Create a new user called "djangoadmin", which can login from localhost, with password "your_password":
`$ mysql> create user 'djangoadmin'@'localhost' identified by 'your_password';
`$ Query OK (0.01 sec)
6. Now give your djangoadmin account permissions. Django will need at least CREATE, DELETE, INSERT, SELECT, UPDATE.
*DROP is also reccomended if you plan on **ever** squashing your migrations (i.e. it's advised to avoid a headache later!). 
`$mysql> grant CREATE, DELETE, INSERT, SELECT, UPDATE, DROP on *.* to 'djangoadmin'@'localhost';
`$Query OK (0.01 sec)
`$mysql> quit
7. Now edit your settings.base file DATABASE options,
`$      'NAME': 'database_name', //this should be whatever you named it in setup (step 4).
`$       'USER': 'djangoadmin', //the user you just made
`$       'PASSWORD': 'your_password', //their password
8. Now cd back over to your project directory, so you can use manage.py:`$ python manage.py migrate` creates your initial migrations!
9. Now add all your code & you're good to go!


### Detailed instructions

Take a look at the docs for more information.
Also checkout:
[Python](https://www.python.org/)
[Django](https://www.djangoproject.com/)

## This project currently borrows heavily from the [Edge project](https://github.com/arocks/edge). Check it out!
