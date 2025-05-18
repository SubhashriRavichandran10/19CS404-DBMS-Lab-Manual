## Experiment 1: Entity-Relationship (ER) Diagram

# 🎯 Objective:

To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

# 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

# 🧪 Choose One Scenario:
# 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

# User Requirements:

* Academic programs grouped under departments.


* Students have admission number, name, DOB, contact info.

* Instructors with staff number, contact info, etc.

  
* Courses have number, name, credits.

* Track course enrollments by students and enrollment date.
  
* Add support for prerequisites (some courses require others).

# 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

# User Requirements:

* Patient details including contact and insurance.
* Doctors and their departments, contact info, specialization.
* Appointments with reason, time, patient-doctor link.
* Medical records with treatments, diagnosis, test results.
* Billing and payment details for each appointment.



# 📝 Tasks:
1.Identify entities, relationships, and attributes.

2.Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).

3.Include:
 * Cardinality & participation constraints
 * Prerequisites for University OR Billing for Hospital


4.Explain:
 * Why you chose the entities and relationships.
 * How you modeled prerequisites or billing.

   
# ER Diagram Submission
# Scenario Chosen:

University

# ER Diagram:

![image](https://github.com/user-attachments/assets/9ee479c4-97d5-4bbd-9615-6243abd915ed)



# Entities and Attributes:

# STUDENT
* Stu_id (PK)
* Full_name
* DOB
* Phone_no
* Email
* FK: Prog_id
# PROGRAM
* Prog_id (PK)
* Prog_name
* FK: Dept_ID
# ENROLLMENT
* Enroll_ID (PK)
* Enrollment_date
* FK: Stu_id
* FK: Course_id
# COURSE
* Course_id (PK)
* Course_name
* Credit
* FK: Prog_id
* FK: Instructor_id
# DEPARTMENT
* Dept_ID (PK)
* Dept_name
# INSTRUCTOR
* Instructor_id (PK)
* Name
* Phone_no
* Email
* FK: Dept_ID
# Relationships and Constraints:
# Relationships
* STUDENT — PROGRAM: Many to One
* PROGRAM — DEPARTMENT: Many to One
* STUDENT — COURSE: Many to Many (via ENROLLMENT)
* COURSE — INSTRUCTOR: Many to One
* INSTRUCTOR — DEPARTMENT: Many to One
* PROGRAM — COURSE: One to Many
* DEPARTMENT — INSTRUCTOR: One to Many
# Cardinality & Constraints
* A student registers for exactly one program.
* A program belongs to one department.
* Each course is part of one program.
* Each course is taught by one instructor.
* Each instructor belongs to one department.
* A student can enroll in many courses, and a course can have many students (via ENROLLMENT).
* Enrollment entity holds the enrollment date and links a student to a course.
# Extension (Optional Enhancements):
# Schedule Entity (Optional)
# New Entity: SCHEDULE
   * Attributes: ScheduleID (PK), Instructor_id (FK), Day, StartTime, EndTime
# Relationship:
   * One Instructor → Many Schedules
# Justification:
   * Allows capturing detailed time availability per instructor.
# Design Justification:
   * Entity Choices and Justifications
# STUDENT
   * Captures individuals pursuing education.
   * Attributes ensure identity, contact, and academic mapping.
# PROGRAM
   * Represents the academic track a student is enrolled in.
   * Linked to departments for structural clarity.
# COURSE
   * Academic units under programs.
   * Tied to instructors and enrollments.
# ENROLLMENT
   * Resolves the many-to-many between students and courses.
   * Tracks course enrollment events.
# DEPARTMENT
   * Groups instructors and programs.
   * Simplifies academic administration.
# INSTRUCTOR
   * Faculty or teaching staff.
   * Linked to courses and departments.
# RESULT
Successfully designed an ER diagram for the University Academic System with entities, relationships, constraints, and optional enhancements to support real-world academic operations.
