# Database Design Documentation

## Introduction
This document provides an overview of the database design for a student management system. The system includes tables for courses, coordinators, mentors, students, batches, tasks, query handler events, completed tasks, pending tasks, and performance tracking.

# Student Management System Database Design

## Entity-Relationship Diagram (ERD)

Below is the Entity-Relationship Diagram representing the database design for the Student Management System.

```plaintext
+---------------------+    +-----------------------+    +---------------------+
|       Courses       |    |      Coordinators     |    |        Mentors      |
+---------------------+    +-----------------------+    +---------------------+
| PK: course_id       |    | PK: coor_id           |    | PK: mentor_id       |
|     course_name      |    |     coor_name         |    |     mentor_name     |
|                     |    | FK: course_id          |    | FK: course_id       |
|                     |    | FK: mentor_id          |    |     course_name     |
+---------------------+    +-----------------------+    +---------------------+
           |                          |                          |
           |                          |                          |
           v                          v                          v
+---------------------+    +-----------------------+    +---------------------+
|       Students      |    |        Batches         |    |        Tasks        |
+---------------------+    +-----------------------+    +---------------------+
| PK: student_id      |    | PK: batch_id           |    | PK: task_id         |
|     student_name    |    |     batch_name         |    |     task_name       |
|     batch_id        |    | FK: course_id          |    |     task_description|
| FK: course_id       |    | FK: mentor_id          |    |     deadline        |
| FK: coor_id         |    | FK: coor_id            |    | FK: coor_id         |
| FK: mentor_id       |    | FK: student_id         |    | FK: mentor_id       |
|                     |    | FK: course_id          |    | FK: student_id      |
|     task_mark       |    +-----------------------+    +---------------------+
+---------------------+              |                          |
                    +---------------+--------------------------+
                    |
          +-------------------------+
          | Query Handler Events    |
          +-------------------------+
          | PK: event_id            |
          |     event_name          |
          |     event_description   |
          | FK: mentor_id           |
          | FK: coor_id             |
          | FK: student_id          |
          +-------------------------+
                    |
          +-------------------------+
          | Chandru Completed Tasks |
          +-------------------------+
          | FK: task_id             |
          | FK: student_id          |
          |     completion_date     |
          +-------------------------+
                    |
          +-------------------------+
          |      Pending Tasks       |
          +-------------------------+
          | FK: task_id             |
          | FK: student_id          |
          |     deadline            |
          +-------------------------+
                    |
          +-------------------------+
          |        Performance       |
          +-------------------------+
          | PK: student_id          |
          |     total_score          |
          |     achievements         |
          +-------------------------+

**Submitted By:**
Chandru Vijayakumar
```
## Modifications
- Added Column to Students Table:
  - `task_mark` (Integer)

## Feedback
🌟 Great database design! The relationships between tables are well-established, and the schema is comprehensive. The inclusion of performance tracking adds valuable insights. Keep up the good work! 🚀

**Submitted By:**
Chandru Vijayakumar
