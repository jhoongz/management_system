# Project Management System

This project is a Project Management System created with Django. It allows users to manage projects, assign tasks, set deadlines, and track project progress.

## Features
- Creation, editing, and deletion of projects.
- Assignment of tasks to projects.
- Setting deadlines for tasks.
- Tracking progress of projects and tasks.
- Intuitive and user-friendly interface.

## Technologies Used
- Django
- HTML
- CSS
- JavaScript

## Installation
1. Clone this repository: `git clone https://github.com/jhoongz/project_management_system.git`
2. Install the dependencies: `pip install -r requirements.txt`
3. Perform database migrations: `python manage.py migrate`
4. Start the server: `python manage.py runserver`

## Usage
- To access the system, open your browser and visit `http://localhost:8000`
- Use the interface to create, edit, and manage projects and tasks.

## Load Sample Data
To load the sample data into the database, follow these steps:
1. Open a terminal in the root directory of your project.
2. Run the following command to start the Django shell:

`python manage.py shell`

## Once in the Django shell, copy and paste the following code to load the sample data:

`
- from django.contrib.auth.models import User
- from projects.models import Project, Task
- from datetime import date

# Create users (if they do not already exist in the database)
manager1, _ = User.objects.get_or_create(username='manager1')
manager2, _ = User.objects.get_or_create(username='manager2')
manager3, _ = User.objects.get_or_create(username='manager3')

# Create projects
project1 = Project.objects.create(
    name='Web Application Development',
    description='Creating a web application using Django and React.',
    start_date=date(2023, 1, 15),
    end_date=date(2023, 6, 30),
    manager=manager1
)

project2 = Project.objects.create(
    name='CRM System Implementation',
    description='Implementing a CRM system for managing customers and sales.',
    start_date=date(2023, 3, 10),
    end_date=date(2023, 9, 30),
    manager=manager2
)

project3 = Project.objects.create(
    name='Cloud Migration',
    description='Migrating server infrastructure to the cloud using AWS.',
    start_date=date(2023, 5, 1),
    end_date=date(2023, 11, 30),
    manager=manager3
)

# Create tasks (optional)
task1 = Task.objects.create(
    project=project1,
    name='Database Design',
    description='Designing the database structure for the web application.',
    assigned_to=manager1,
    due_date=date(2023, 2, 15),
    completed=False
)

task2 = Task.objects.create(
    project=project2,
    name='Initial CRM Setup',
    description='Setting up and customizing the CRM according to the company needs.',
    assigned_to=manager2,
    due_date=date(2023, 4, 10),
    completed=False
)

task3 = Task.objects.create(
    project=project3,
    name='Cloud Server Configuration',
    description='Configuring servers in the cloud using AWS.',
    assigned_to=manager3,
    due_date=date(2023, 6, 1),
    completed=False
)
`

## Contribution
If you want to contribute to this project, please create a new branch for your changes and submit a pull request with your improvements.

## License
This project is licensed under the MIT License. For more details, see the LICENSE file.

