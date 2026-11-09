# Project 4 – Container Description

**Name:** Kye'Marrion Thomas  
**Course:** CSCI 4221 – Software Engineering  
**Group:** 5  
**Project:** Study Habit Tracker

## System Overview

The Study Habit Tracker is a cloud-based application designed to help students create study goals, log study sessions, and monitor their progress.

The application is organized into separate components so each feature can be developed and maintained independently.

## Container Architecture

The proposed system uses Docker containers to package the application and its dependencies.

The architecture includes three main parts:

1. **Frontend Container:** Displays the user interface, including study goals, study history, and progress toward goals.
2. **Backend Container:** Processes study session information, calculates goal progress, and communicates with the database.
3. **Database Container:** Stores student accounts, study goals, and completed study sessions.

## My Assigned Component

My assigned component is **Show Progress Toward Goals**.

This component will:

- Retrieve a student's study goals.
- Read completed study-session records.
- Calculate progress toward each goal.
- Display completed hours and progress percentages.

## Example Data Flow

1. A student opens the Goal Progress page.
2. The frontend requests progress information from the backend.
3. The backend retrieves goal and study-session data.
4. The backend calculates the percentage completed.
5. The frontend displays the student's progress.

## Proposed Deployment

The application can be deployed to a cloud server using Docker containers. The containers communicate through a private application network, with the backend managing database access.

This is a proposed architecture for Project 4, not a claim that the application has already been deployed.
