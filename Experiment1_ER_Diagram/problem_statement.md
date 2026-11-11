# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.

---

# Scenario A: City Fitness Club Management

**Business Context:**  
FlexiFit Gym wants a database to manage its members, trainers, and fitness programs.

**Requirements:**  
- Members register with name, membership type, and start date.  
- Each member can join multiple programs (Yoga, Zumba, Weight Training).  
- Trainers assigned to programs; a program may have multiple trainers.  
- Members may book personal training sessions with trainers.  
- Attendance recorded for each session.  
- Payments tracked for memberships and sessions.

### ER Diagram:
<img width="1714" height="918" alt="scenario1" src="https://github.com/user-attachments/assets/587bef98-9e28-46fb-b3c3-810c953fac89" />



### Entities and Attributes

| **Entity** | **Attributes (PK, FK)** | **Notes** |
| --- | --- | --- |
| **Member** |Member_ID *(PK)*, Name, Membership_Type, Start_Date | Stores member details and membership information. |
| **Program** | Program_ID *(PK)*, Program_Name, Description | Stores fitness programs offered by the gym, such as Yoga, Zumba, and Weight Training. |
| **Trainer** | Trainer_ID *(PK)*, Name, Specialization |Stores trainer details and their areas of specialization. |
| **Personal Training Session** | Session_ID *(PK)*, Session_Date, Time_Slot | Stores personal training session details and schedules. |
| **Attendance** | Attendance_ID *(PK)*, Attendance_Date, Status |Tracks member attendance for scheduled sessions. |
| **Payment** | Payment_ID *(PK)*, Amount, Payment_Date |Records payments made by members for memberships and training sessions. |

### Relationships and Constraints

| **Relationship**       | **Cardinality** | **Participation**          | **Notes** |
|------------------------|-----------------|----------------------------|-----------|
| Member–Program         | M : N           | Optional                   | A member can join multiple fitness programs, and each program can have multiple members. |
| Program–Trainer        | M : N           | Optional                   | A trainer can be assigned to multiple programs, and each program can have multiple trainers. |
| Member–Session         | 1 : M           | Optional                   | A member can book multiple sessions, and each session is booked by one member. |
| Trainer–Session        | 1 : M           | Total on Session side      | A trainer can conduct multiple sessions, and each session is conducted by one trainer. |
| Session–Attendance     | 1 : M           | Total on Attendance side   | Each session can have multiple attendance records, and each attendance record belongs to one session. |
| Member–Payment         | 1 : M           | Total on Payment side      | A member can make multiple payments, and each payment belongs to one member. |

### Assumptions


1. Each member is uniquely identified using Member_ID.
2. Members provide their name, membership type, and start date during registration.
3. A member can join multiple fitness programs, such as Yoga, Zumba, and Weight Training.
4. Each fitness program can have multiple members enrolled.
5. Trainers can be assigned to multiple fitness programs.
6. Each trainer has a unique Trainer_ID and a specific specialization.
7. Each personal training session is uniquely identified using Session_ID.
8. Each session is booked by one member and conducted by one trainer.
9. Attendance records are maintained to track whether members are Present or Absent.
10. Members can make multiple payments for memberships and personal training sessions.


# Scenario B: City Library Event & Book Lending System

**Business Context:**  
The Central Library wants to manage book lending and cultural events.

**Requirements:**  
- Members borrow books, with loan and return dates tracked.  
- Each book has title, author, and category.  
- Library organizes events; members can register.  
- Each event has one or more speakers/authors.  
- Rooms are booked for events and study.  
- Overdue fines apply for late returns.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_library.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

# Scenario C: Restaurant Table Reservation & Ordering

**Business Context:**  
A popular restaurant wants to manage reservations, orders, and billing.

**Requirements:**  
- Customers can reserve tables or walk in.  
- Each reservation includes date, time, and number of guests.  
- Customers place food orders linked to reservations.  
- Each order contains multiple dishes; dishes belong to categories (starter, main, dessert).  
- Bills generated per reservation, including food and service charges.  
- Waiters assigned to serve reservations.

### ER Diagram:
*Paste or attach your diagram here*  
![ER Diagram](er_diagram_restaurant.png)

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |
|        |                    |       |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
|              |            |               |       |
|              |            |               |       |
|              |            |               |       |

### Assumptions
- 
- 
- 

---

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
