# Project 4 – Database Table Structure

**Name:** Kye'Marrion Thomas  
**Course:** CSCI 4221 – Software Engineering  
**Group:** 5  
**Project:** Study Habit Tracker

## Database Overview

The Study Habit Tracker will use a relational database to store student information, study goals, and completed study sessions.

The proposed database includes three tables: Students, StudyGoals, and StudySessions.

## Table 1: Students

| Column | Data Type | Description |
|---|---|---|
| student_id | INTEGER | Primary Key |
| student_name | VARCHAR(100) | Student's name |
| email | VARCHAR(150) | Student's email address |

## Table 2: StudyGoals

| Column | Data Type | Description |
|---|---|---|
| goal_id | INTEGER | Primary Key |
| student_id | INTEGER | Foreign Key referencing Students |
| goal_name | VARCHAR(100) | Name of the study goal |
| target_hours | DECIMAL(6,2) | Target study hours |
| start_date | DATE | Goal start date |
| end_date | DATE | Goal deadline |

## Table 3: StudySessions

| Column | Data Type | Description |
|---|---|---|
| session_id | INTEGER | Primary Key |
| student_id | INTEGER | Foreign Key referencing Students |
| goal_id | INTEGER | Foreign Key referencing StudyGoals |
| session_date | DATE | Date of study session |
| duration_minutes | INTEGER | Completed study time in minutes |

## Table Relationships

- One student can have multiple study goals.
- One student can record multiple study sessions.
- One study goal can have multiple study sessions.
- Each study session can be associated with a study goal.

## My Component: Show Progress Toward Goals

My component uses the StudyGoals and StudySessions tables to calculate each student's progress.

The system retrieves the target hours from StudyGoals and adds the completed session durations from StudySessions.

## Example Progress Calculation

A student creates a goal to study for 10 hours.

The student completes three study sessions:

- Session 1: 120 minutes
- Session 2: 180 minutes
- Session 3: 60 minutes

Total completed time = 360 minutes = 6 hours.

Progress = (6 / 10) × 100 = 60%

The application displays 60% progress toward the goal.

## Example SQL Query

```sql
SELECT
    g.goal_id,
    g.goal_name,
    g.target_hours,
    COALESCE(SUM(s.duration_minutes), 0) / 60.0
        AS completed_hours
FROM StudyGoals g
LEFT JOIN StudySessions s
    ON g.goal_id = s.goal_id
    AND g.student_id = s.student_id
WHERE g.student_id = 1
GROUP BY g.goal_id, g.goal_name, g.target_hours;
```

## Database Design Notes

- Primary keys uniquely identify records.
- Foreign keys connect students, goals, and study sessions.
- Session durations are stored in minutes for consistent calculations.
- Target hours must be greater than zero.
- The database structure is a proposed design for Project 4 and has not yet been implemented.
