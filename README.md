```

CREATE DATABASE SchoolDB CHARACTER SET utf8mb4;
USE SchoolDB;
```

```
CREATE TABLE Classrooms (
    classroom_id INT PRIMARY KEY,
    classroom_name VARCHAR(50),
    teacher_id INT
);

CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    student_name VARCHAR(50),
    classroom_id INT,
    grade INT,
    gender VARCHAR(10),
    FOREIGN KEY (classroom_id) REFERENCES Classrooms(classroom_id)
);
```
```
ALTER TABLE Students
ADD COLUMN Gender VARCHAR(10);
```
```

INSERT INTO Students VALUES (1, 'Student1', 1, 90, 'Male');
```

```

UPDATE Students SET Age = Age + 1 WHERE Classroom_id = 10 AND Age BETWEEN 10 AND 16;

```

```

DELETE FROM Students WHERE Age < 10;

```

```

SELECT FirstName, LastName, Age FROM Students;

```

```

SELECT AVG(Age) AS AverageAge FROM Students;
```
 
```

ALTER TABLE Students
ADD PRIMARY KEY (StudentID);
```
Create Foreign Key:
A foreign key establishes a link between two tables, enforcing referential integrity.

```

        CREATE TABLE Courses (
            CourseID INT PRIMARY KEY,
            CourseName VARCHAR(50)
        );

        ALTER TABLE Students
        ADD FOREIGN KEY (CourseID) REFERENCES Courses(CourseID);
```
    SQL Queries:

    List all students with their respective classrooms and teacher names:

```

SELECT Students.student_name, Classrooms.classroom_name, Classrooms.teacher_name
FROM Students
JOIN Classrooms ON Students.classroom_id = Classrooms.classroom_id;
```
 
```
SELECT Classrooms.classroom_name, AVG(Students.grade) AS AverageGrade
FROM Students
JOIN Classrooms ON Students.classroom_id = Classrooms.classroom_id
GROUP BY Classrooms.classroom_name;
```
 
```
SELECT Students.student_name
FROM Students
JOIN Classrooms ON Students.classroom_id = Classrooms.classroom_id
WHERE Classrooms.teacher_id = 123;
```
 
```

SELECT Classrooms.classroom_name, COUNT(Students.student_id) AS NumberOfStudents
FROM Classrooms
LEFT JOIN Students ON Classrooms.classroom_id = Students.classroom_id
GROUP BY Classrooms.classroom_name;
```
 
```
    SELECT Classrooms.classroom_name, AVG(Students.grade) AS AverageGrade
    FROM Students
    JOIN Classrooms ON Students.classroom_id = Classrooms.classroom_id
    GROUP BY Classrooms.classroom_name
    HAVING AVG(Students.grade) > 80;
```

# DDL Commands:
# Create a Database:
Task: Create a new database named "SchoolDB" with an appropriate character set.
# Create Tables:

Task: Design and create a table named "Students" with the following columns:
# Classrooms:

classroom_id (Primary Key)
classroom_name
teacher_id

#  Students:
student_id (Primary Key)
student_name
classroom_id (Foreign Key referencing classroom_id in the "Classrooms" table)
grade

# Modify Table Structure:

Task: Add a new column named "Gender" (VARCHAR, Maximum 10 characters) to the "Students" table.

# DML Commands:
Insert Data:

Task: Insert at least 5 records into the "Students" table.
# Update Records:

Task: Update the "Age" of students who are in the "Class" 10 to 16.
# Delete Records:

Task: Delete all records of students whose "Age" is less than 10.
# DQL Command:
# Select Data:

Task: Write a SELECT query to retrieve the "FirstName," "LastName," and "Age" of all students in the "SchoolDB."
# Aggregate Functions:

Task: Use aggregate functions to find the average age of all students.

# Primary Key and Foreign Key:
# Define Primary Key:

Task: Explain the concept of a primary key and its significance. Also, ensure that the "StudentID" column in the "Students" table is a primary key.
# Create Foreign Key:

Task: Create a new table named "Courses" with columns: "CourseID" (Integer, Primary Key) and "CourseName" (VARCHAR, Maximum 50 characters). Then, add a foreign key constraint in the "Students" table referencing the "CourseID" in the "Courses" table.


Write SQL queries to perform the following tasks:

# List all students with their respective classrooms and teacher names.

# Show the average grade for each classroom. Display the classroom name and the average grade.

# Find the names of students who belong to a classroom taught by a specific teacher (you can choose a teacher_id).

# List all classrooms along with the number of students in each classroom.

# Show the details of classrooms that have an average grade above a certain value (you can choose a specific grade).
