# Project 4 – Components and Necessary Files

**Name:** Kye'Marrion Thomas  
**Group:** 5  
**Project:** Study Habit Tracker

## System Components

The proposed Study Habit Tracker application contains three main features:

1. **Goal Setting – Kamani Mccalla**
   - Allows students to create and manage study goals.
   - Stores goal information for progress tracking.

2. **Logging Study Sessions – Jayla Menefee**
   - Allows students to record completed study sessions.
   - Stores study duration and session dates.

3. **Show Progress Toward Goals – Kye'Marrion Thomas**
   - Retrieves study goals and completed study sessions.
   - Calculates progress toward each study goal.
   - Displays completed study hours and progress percentages.

## My Component: Show Progress Toward Goals

My component is responsible for showing students how close they are to completing their study goals.

### Inputs
- Student ID
- Goal ID
- Target study hours
- Completed study-session durations

### Processing
1. Retrieve the selected study goal.
2. Retrieve study sessions associated with that goal.
3. Calculate total completed study hours.
4. Calculate the percentage of the goal completed.
5. Return the results to the user interface.

### Outputs
- Goal name
- Target study hours
- Completed study hours
- Progress percentage
- Progress bar

## Proposed Necessary Files

| File | Purpose |
|---|---|
| `GoalProgress.jsx` | Displays goal progress to students |
| `progressController.js` | Handles progress requests |
| `progressService.js` | Calculates completed hours and percentages |
| `progressRoutes.js` | Defines backend API routes |
| `database.js` | Manages database connections |

These filenames represent a proposed component design. They are not yet implemented application files.

## Progress Calculation

Progress Percentage = (Completed Study Hours / Target Study Hours) × 100

For example, if a student completes 6 hours toward a 10-hour study goal:

Progress = (6 / 10) × 100 = 60%

If a goal has zero target hours, the application must handle that case without dividing by zero.

## Component Dependencies

The Show Progress Toward Goals component depends on:

- Goal information from the Goal Setting feature
- Completed study sessions from the Logging Study Sessions feature
- Backend services for progress calculations
- Database access for retrieving stored information
