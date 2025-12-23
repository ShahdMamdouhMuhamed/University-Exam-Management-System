# University-Exam-Management-System
📌 Project Overview

The University Exam Management System is an Oracle PL/SQL–based project designed to automate and manage university exam processes.
It handles course registration validation, exam scheduling, grade calculation, student performance tracking, warnings, suspensions, and full auditing of critical operations.

This project is implemented according to the official task description provided in the assignment document.

🗂️ Database Tables

The system is built using the following tables:

Courses
Stores course details, assigned professors, credit hours, and prerequisite courses.

Professors
Contains professor information and departments.

Students
Stores student data, academic status, and total credit hours.

Register
Tracks course registrations for students.

Exams
Manages exam schedules and types (midterm, final).

ExamResults
Stores exam grades and pass/fail status.

Warnings
Logs warnings issued to students due to poor performance.

AuditTrail
Records all important insert, delete, and update operations.

DBUserCreationLog
Logs database user creation activities.

⚙️ System Features
1️⃣ User Management and Privileges

Creation of a Manager User responsible for creating two users.

User 1 creates the Students and Courses tables.

User 2 inserts student data and course registrations.

A PL/SQL procedure logs every newly created database user into DBUserCreationLog.

2️⃣ Exam Eligibility Validation

A BEFORE INSERT trigger on the Register table.

Ensures students meet course prerequisite requirements.

Prevents registration if prerequisites are not completed.

3️⃣ Grade Calculation

A PL/SQL function calculates letter grades based on score ranges.

Updates the ExamResults table and returns the calculated grade.

4️⃣ Automated Warning Issuance

A procedure checks students who failed two or more courses.

Automatically inserts warning records into the Warnings table.

5️⃣ Audit Trail for Registration

BEFORE INSERT and BEFORE DELETE triggers on the Register table.

Logs all registration and deregistration events into AuditTrail.

6️⃣ Course Performance Report

A PL/SQL cursor generates a report for a specific course.

Displays:

Student IDs

Grades

Number of passed and failed students

7️⃣ Exam Schedule Management

A PL/SQL block retrieves exam schedules for a selected course.

Displays exam date and type.

Shows a message if no exams are scheduled.

8️⃣ Multi-Exam Grade Update with Transactions

Updates multiple exam results in a single transaction.

Uses COMMIT and ROLLBACK to ensure data consistency.

9️⃣ Student Suspension Based on Warnings

A procedure identifies students with three or more warnings.

Updates their academic status to Suspended.

Logs the update in the AuditTrail table.

🔟 Advanced Grade Management and Data Integrity

A function calculates the student’s GPA using:

Exam results

Course credit hours

A trigger restricts grade updates to authorized users only.

⭐ Bonus Tasks

Demonstrates a blocker–waiting transaction scenario using two users.

Identifies blocker and waiting sessions using SID and SERIAL#.

Explains how the locking issue is resolved.

🛠️ Requirements

Oracle Database

Oracle SQL Developer (or similar tool)

Knowledge of:

PL/SQL

Triggers

Cursors

Transactions

Roles and Privileges

📁 Notes

All scripts are written in one Oracle SQL file.

Code is fully commented and documented.

All team members should understand every task and concept.
