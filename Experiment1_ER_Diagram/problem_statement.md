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

| **Relationship** | **Cardinality** | **Participation** | **Notes** |
| --- | --- | --- | --- |
| Member–Program | M : N | Optional | A member can enroll in multiple programs; each program can have many members. |
| Program–Trainer | N : M | Optional | Trainers can be assigned to multiple programs; programs can have multiple trainers. |
| Program–Session | M : N | Total on Session side | Each program consists of multiple sessions; sessions belong to programs. |
| Member–Session | M : N | Optional | Members can book multiple sessions; sessions can be attended by multiple members. |
| Session–Payment | N : 1 | Total on Payment side | Payments are linked to sessions; one payment may cover multiple sessions. |
| Trainer–Attendance | 1 : M | Total | A trainer manages attendance records for sessions they conduct. |
| Attendance–Member | 1 : N | Total | Attendance records are tied to members and sessions. |

### Assumptions
- A Trainer can specialize in multiple areas and may lead multiple programs.

- Session ID uniquely identifies each scheduled workout session.

- Payment Type could be Cash, Card, Online, etc.

- A member can miss sessions without losing membership, but attendance is still recorded.
---

---

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
