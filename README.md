# Capstone Databases Workshop

In this workshop we will focus on two things:

- Setting up and running/writing basic databases and queries
- Understanding how to plan new databases for applications that need to represent interconnected data

## Slides for the session

The slides for this session can be found here: [https://docs.google.com/presentation/d/1OfTlH4PSthmpPD1WQcHLMA8rEWUMYFtMo5coIsReaTw/edit?usp=sharing](https://docs.google.com/presentation/d/1OfTlH4PSthmpPD1WQcHLMA8rEWUMYFtMo5coIsReaTw/edit?usp=sharing) 

## Obtaining the code

You can just download this repository as a .zip file if you do not have Git and GitHub setup.

You may wish to make a fork of this repository if you want to have your own version in GitHub. To clone this repository or your forked repository onto your machine, click the green `Code` button, make sure `HTTPS` is selected, then click the `copy` button to the right of the web URL to copy its value. Then, clone onto your local machine from a terminal, using the `git clone` command. Alternatively, you may download a .zip version of the repository if you do not have Git configured on your computer.

If this is the first time you've ever cloned a repository on the current machine, you may be asked to enter your GitHub credentials. The "sign in with your browser" option should work just fine. You may need to enter your GitHub username and password, and / or authorize "git credential manager" to access your account. Perform these steps if asked.

Now, you should have a clone of your repository on your local machine, ready to develop!

## Getting started

Before you can begin executing your SQL, you'll need a program which can create and access SQLite databases. For this session, we recommend using the SQLiteStudio. Installers for Windows, Mac, and other platforms are available on the tool's website ([https://sqlitestudio.pl/](https://sqlitestudio.pl/)). For Windows, the *"PortableApp"* version is a single `.exe` file which you can put anywhere, so it is very convenient. Alternatively you may wish to investigate DB Browser for SQLite or a range of IDE plugins.

To setup we will start by doing the following within SQLiteStudio or whatever database application you are using:

- Create a new `.db` file within the `example-unidb.db` directory
- Connect to the database
- Open and run the `uni-db.sql` file to generate the data
- Open the `your-queries.sql` file to practice writing some queries for the database you created

It is not practical to include detailed steps for this or using SQLiteStudio within this readme, so please pay attention to the live demos and/or use online reference information to learn how to use the relevant software.

## Exercise One &ndash; SQL queries with the `uni-db.sql` database

In this exercise, you will be using the database you created using the `uni-db.sql` file. Remember that you can reset the database at any time by re-running the associated SQL script.

You should write all of your queries within the `your-queries.sql` file and save this file as this will allow you to refer back to them later.

Start by testing some of the basic queries that are in the lecture slides; it is suggested that you at least try to:

- Select all students
- Select all lecturers
- Practice a join where you select both the student and attends data by joining the student and attends table

#### Advanced queries 

You may not have time to do all of these in the workshop, but they have been included here as extra practice.

Develop SQL statements that answer the following questions:

* What are the names of the students who attend COMP219?
* What are the names of the student reps that are not from NZ?
* Where are the offices for the lecturers of 219?
* What are the names of the students taught by Te Taka?
* List the students and their mentors
* Name the lecturers whose office is in G-Block as well as naming the students that are not from NZ
* List the course coordinator and student rep for COMP219


# Planning and modelling databases

For this section, this will relate to creating ER diagrams and relational schemas as covered by the lecture slides. You may only get time to create and plan the diagrams on paper or any planning software like draw.io, but it is suggested that you find time to practice creating the SQL for these in your own time. Remember that for a database to be properly structured, you must carefully model one-to-many and many-to-many relationships with  primary and foreign keys as required. Many-to-many relationships will always require an extra table to structure the relationship, so make sure to plan carefully and think about which relationships between entities will be one-to-many and which will be many-to-many.

It is not important to finish both tasks below; however, it is important that you complete the plan for at least one of the databases below, so that you are prepared to create plans for new databases that may be required for full stack applications in projects you will create.

## Exercise Two &ndash; Modelling an employee database

In this exercise you will create an ER diagram, relational schema and SQL required for the database outlined below. Read the explanation carefully and use the UniDB example from the lecture slides to help you review how to structure your ER diagram and relational schema.

A business wants to store information about its **employees**, **departments** and **vehicles**. This business has multiple departments. Employees can work in one or more departments. Each department has exactly one employee that is a manager. This means that managers are also normal employees in the database. Managers can manage more than one department. The business also has vehicles that must belong to only one department; not every department has vehicles but some departments have more than one vehicle.

The company needs to store all of this information in its database:

- The full name of all employees
- The age of all employees
- A description of the role each employee has in every department they work in
- The license plate number for vehicles
- Types of all vehicles
- Age for all vehicles (year they were made)
- The name and description of each department as well as who manages each department

### Tasks

1. Draw an ER Diagram for this database. You may use pen-and-paper, or the diagramming tool of your choice. Save a copy in the [`ex01`](./exercises/ex01) folder for your later reference (scan or photograph it if you hand-drew it).
2. Write a relational schema for this database. You may hand-write this or use a text editor of your choice. Save a copy in the `ex01` folder for your later reference.
3. In the `ex01/exercise01.sql` file, write the SQL required to create this database.
4. Populate the database with some sample data. You should have at least 3 departments, 9 employees and 6 vehicles in your sample data. Examples for department names could be 'landscaping', 'resedential', 'commercial'. You can make up your own vehicle types and employee names etc.
5. Using the SQLite DB Browser tool, create a new database and run your SQL script to create the tables and data.
6. Write two queries to select:
   - Employees from just one department
   - Just employees who are under 30

## Exercise Three &ndash; Modelling a blogging system

This is a more open task, get creative and try to think up of more advanced features and model the database tables for these. 

Design a database for a blogging system that is able to have users that create articles. Users can like articles by other authors, but they can only like each article once; an article can be liked by many other users. Users can comment on articles and comment on comments with unlimited levels of nesting. Users can upvote and downvote comments. Users can follow and be followed by other users. Users can instant message other users and message histories are saved. Users can block other users which will prevent that user from messaging them or commenting on articles.
