# Web Lab &ndash; Database Modelling &amp; Advanced SQL Queries
In this lab, we practice more advanced SQL queries, selecting data from multiple tables at once. We also investigate database design using ER diagrams and the relational model.

## Obtaining the code
Now that you've obtained a copy of this repository through GitHub Classroom's invite, you have your own private version of this repository (i.e. the one you're looking at now)! To clone this repository onto your machine, click the green `Code` button, make sure `HTTPS` is selected, then click the `copy` button to the right of the web URL to copy its value. Then, clone onto your local machine from a terminal, using the `git clone` command.

If this is the first time you've ever cloned a repository on the current machine, you may be asked to enter your GitHub credentials. The "sign in with your browser" option should work just fine. You may need to enter your GitHub username and password, and / or authorize "git credential manager" to access your account. Perform these steps if asked.

Now, you should have a clone of your repository on your local machine, ready to develop!

Remember to commit and push your work regularly for backup purposes. It's also really good practice to create new branches for each exercise, and merge these into `main` using a Pull Request (PR) when they're complete (as opposed to simply pushing directly to `main` each time). This will get you used to a collaborative workflow style that will come in really handy when working on the final team project this semester!


## Getting started
Before you can begin executing your SQL, you'll need a program which can create and access SQLite databases. For this lab, we'll use the SQLite Database browser. Installers for Windows, Mach, and other platforms are available on the tool's website (<https://sqlitebrowser.org/dl/>). For Windows, the *"PortableApp"* version is a single `.exe` file which you can put anywhere, so it is very convenient.


## Exercise One &ndash; Modelling an employee database
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


## Exercise Two &ndash; Modelling a film database
In this exercise, we will repeat the steps of Exercise One for a different database that will have a different structure. 

We wish to store information about actors, films, genres, film directors and production companies. Within our database:
- An actor can be involved in many films
- A film can have many actors
- A film can only belong to one genre but many films can be the same genre
- A film can have many directors
- A director can direct many films
- A film can only have one production company
- A production company can produce many films

Each entity will have attributes associated with it:
- Movies have titles, lengths, years, plot outlines
- A genre has a name and a description
- Actors have full names and dates of birth
- Directors have full names and dates of birth
- Production companies have names and addresses

### Tasks
1. Design an ER diagram that captures these relationships
2. Write a relational schema for this database
3. In the `ex02/exercise02.sql` file, write a complete SQL database schema to create this database
4. Populate the database with some sample data. You should have at least 10 films in your database along with all of the information for the films' directors, actors (only create a small amount of sample data for actors), genres and production companies. You could Google a top-10 list of movies to get your sample data.
5. Create a new database using the DB Browser tool, and run your script against it.


## Exercise Three &ndash; Intermediate SQL queries
For Exercises Three and Four, you'll be writing queries to extract data from the UniDB database that's been provided to you. Begin by studying the [`uni-db.sql`](./examples/uni-db.sql) file. This creates a database very similar to the one examined in the lectures, which we will be using in the next two questions. Create a new database in the DB Browser tool and run the script against it to initialize the database, if you have not already done so.

**Remember:** If you need to reset the database for any reason, you can re-run `uni-db.sql` against the database.

Write SQL queries that answer the following questions, placing the answers in the `ex03/exercise03.sql` file for your later reference:

- List the departments which offer courses (A department can be identified by its code, e.g. 'comp', 'ling', etc.)
- List the semesters which are being attended by students
- List the courses that are attended by students (i.e. department plus course number e.g. 'comp 219')
- List the student names and countries, ordered by first name
- List the student names and mentors, ordered by mentors
- List the lecturers, ordered by office
- List the staff whose staff number is greater than 500
- List the students whose id is greater than 1668 and less than 1824
- List the students from NZ, Australia and US
- List the lecturers in G Block
- List the courses *not* from the Computer Science Department
- List the students from France or Mexico


## Exercise Four &ndash; Advanced SQL queries
In this exercise, you will again be using the UniDB database. Remember that you can reset the database at any time by re-running the associated SQL script.

Develop SQL statements that answer the following questions, placing the answers in the `ex04/exercise04.sql` file for later reference:

* What are the names of the students who attend COMP219?
* What are the names of the student reps that are not from NZ?
* Where are the offices for the lecturers of 219?
* What are the names of the students taught by Te Taka?
* List the students and their mentors
* Name the lecturers whose office is in G-Block as well as naming the students that are not from NZ
* List the course coordinator and student rep for COMP219
