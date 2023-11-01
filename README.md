# Scheduler

This is a Django application designed to automate the scheduling process for retail shifts with particular rules and constraints. 

### Constraints
Almost all of the relevant logic is located in [schedulerLogic.py](https://github.com/TomBombadilV/scheduler/blob/master/scheduler/schedulerLogic.py). 
The following constraints were implemented:
1. All employees must work their full assigned hours every week
2. Every employee must work one opening shift and one closing shift per week
3. No employee can work more than five days in a row
4. No employee can have less than 10 hours between shifts
5. There must be an MOD scheduled at all times
6. Every opening shift must have one MOD and two regular staff
7. Every closing shift must have one MOD and three regular staff
8. All shift and vacation requests must be honored
9. All of these constraints must be held from week to week

### Interface Layout
There are four main sections in the application:
* A page to set parameters for the generated schedule
* A page to add, remove, or modify employee information
* A page to add, remove, or modify shift and vacation requests
* A page to view, edit, and delete generated schedules

The application also uses Django's built in user authentication system to allow different permissions for different users so that managers can create and edit schedules while employees can view them.

### Usage
In main project directory:<br>
`python -m venv schedule-test_env`<br>   
`.\schedule-test_env\Scripts\activate`<br>
`pip install django`<br>
`pip install numpy`<br>
`pip install python-dateutil`<br>
`python manage.py makemigrations`<br>
`python manage.py migrate --run-syncdb`<br>
* --run-syncdb - Creates tables for apps without migrations.
`python manage.py runserver`
