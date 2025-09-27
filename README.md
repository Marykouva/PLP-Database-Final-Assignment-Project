StudentDB Database

Description
This project is a **relational database** created using **MySQL** for managing student records and courses. It demonstrates proper database design with:

- Well-structured tables
- Primary and foreign key constraints
- NOT NULL and UNIQUE constraints
- One-to-Many and Many-to-Many relationships

---

Database Name
**StudentDB**

---

 Tables and Relationships

1. Students
| Column     | Data Type       | Constraints                     |
|-----------|----------------|---------------------------------|
| StudentID | INT            | PRIMARY KEY, AUTO_INCREMENT     |
| FirstName | VARCHAR(50)    | NOT NULL                        |
| LastName  | VARCHAR(50)    | NOT NULL                        |
| Email     | VARCHAR(100)   | NOT NULL, UNIQUE                |
| Phone     | VARCHAR(20)    | NULL                            |

2. Courses
| Column     | Data Type       | Constraints                     |
|-----------|----------------|---------------------------------|
| CourseID  | INT            | PRIMARY KEY, AUTO_INCREMENT     |
| CourseName| VARCHAR(100)   | NOT NULL                        |
| Credits   | INT            | NOT NULL                        |

3. Enrollments
| Column        | Data Type    | Constraints                                                |
|---------------|------------|------------------------------------------------------------|
| EnrollmentID  | INT        | PRIMARY KEY, AUTO_INCREMENT                                |
| StudentID     | INT        | NOT NULL, FOREIGN KEY REFERENCES Students(StudentID)      |
| CourseID      | INT        | NOT NULL, FOREIGN KEY REFERENCES Courses(CourseID)        |
| Grade         | VARCHAR(2) | NULL                                                       |
| EnrollmentDate| TIMESTAMP  | DEFAULT CURRENT_TIMESTAMP                                  |
| UNIQUE        |            | Combination of StudentID and CourseID to prevent duplicates|

Relationships:
- **Students → Enrollments** → One-to-Many  
- **Courses → Enrollments** → One-to-Many  
- Many-to-Many between Students and Courses is handled via **Enrollments** table  

---

 How to Run

1. Open **MySQL Workbench** or any MySQL client.  
2. Execute the SQL script `StudentDB.sql` to create the database and tables.  
3. Verify tables and constraints are created correctly by inspecting the database.

---

 Author
Marykouva
