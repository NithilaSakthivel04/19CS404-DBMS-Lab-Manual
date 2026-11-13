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
<img width="1692" height="930" alt="scenariob" src="https://github.com/user-attachments/assets/fc8b10db-5fb2-4ada-8e66-9bb09c242a8f" />


### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| MEMBER | Member_ID (PK), Name, Email, Phone, Join_Date | Library member details |
| BOOK | Book_ID (PK), Title, Author, Category | Book information |
| LOAN | Loan_ID (PK), Member_ID (FK), Book_ID (FK), Loan_Date, Due_Date, Return_Date | Book lending and return tracking |
| FINE | Fine_ID (PK), Loan_ID (FK), Amount, Reason, Payment_Status | Overdue fine details |
| EVENT | Event_ID (PK), Event_Title, Event_Date, Description | Cultural events |
| SPEAKER | Speaker_ID (PK), Name, Affiliation | Speakers and authors |
| EVENT_SPEAKER | Event_ID (PK, FK), Speaker_ID (PK, FK) | Event-speaker relationship |
| REGISTRATION | Registration_ID (PK), Member_ID (FK), Event_ID (FK), Registration_Date, Status | Member event registration |
| ROOM | Room_ID (PK), Room_Name, Capacity | Library room details |
| ROOM_BOOKING | Booking_ID (PK), Room_ID (FK), Event_ID (FK), Booking_Date, Purpose | Room booking for events and study |

### Relationships and Constraints

| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| MEMBER – LOAN | 1 : M | Total – Partial | A member can borrow many books |
| BOOK – LOAN | 1 : M | Total – Partial | A book can be loaned multiple times |
| MEMBER – REGISTRATION | 1 : M | Total – Partial | A member can register for many events |
| EVENT – REGISTRATION | 1 : M | Total – Partial | An event can have many registrations |
| EVENT – SPEAKER | M : N | Total – Total | Each event has one or more speakers |
| ROOM – ROOM_BOOKING | 1 : M | Total – Total | A room can have multiple bookings |
| EVENT – ROOM_BOOKING | 1 : 1 | Partial – Total | An event is booked in a room |
| LOAN – FINE | 1 : 1 | Partial – Total | A loan may incur an overdue fine |

### Assumptions

1. Each library member is uniquely identified by Member_ID.
2. Each book is uniquely identified by Book_ID.
3. A member can borrow multiple books, but each loan record refers to one book.
4. Each book can have multiple loan records over time.
5. A member can register for multiple library events.
6. Each event must have at least one speaker or author.
7. An event can have multiple speakers, and a speaker can participate in multiple events.
8. Each room can be booked for events or study purposes.
9. A loan may generate a fine if the book is returned after the due date.
10. Each loan can have at most one fine record.

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
<img width="1691" height="930" alt="scenarioc" src="https://github.com/user-attachments/assets/7dc6e002-76fa-4104-89f3-6d5d0c22acb8" />

### Entities and Attributes

| Entity | Attributes (PK, FK) | Notes |
|--------|--------------------|-------|
| CUSTOMER | Customer_ID (PK), Name, Phone, Email | Customer details |
| RESERVATION | Reservation_ID (PK), Customer_ID (FK), Table_ID (FK), Waiter_ID (FK), Reservation_Date, Time, No_of_Guests | Table reservation and walk-in details |
| RESTAURANT_TABLE | Table_ID (PK), Table_Number, Capacity, Status | Restaurant table details |
| WAITER | Waiter_ID (PK), Name, Phone | Waiter details |
| FOOD_ORDER | Order_ID (PK), Reservation_ID (FK), Order_Date, Order_Status | Customer food orders |
| ORDER_ITEM | Order_Item_ID (PK), Order_ID (FK), Dish_ID (FK), Quantity, Price | Dishes included in each order |
| DISH | Dish_ID (PK), Category_ID (FK), Dish_Name, Price | Food menu details |
| CATEGORY | Category_ID (PK), Category_Name | Starter, Main, Dessert |
| BILL | Bill_ID (PK), Reservation_ID (FK), Total_Amount, Food_Charge, Service_Charge, Payment_Status | Billing details |

### Relationships and Constraints
| Relationship | Cardinality | Participation | Notes |
|--------------|------------|---------------|-------|
| CUSTOMER – RESERVATION | 1 : M | Partial – Total | A customer can make multiple reservations |
| RESERVATION – RESTAURANT_TABLE | M : 1 | Total – Partial | Each reservation is assigned to one table |
| WAITER – RESERVATION | 1 : M | Partial – Total | A waiter serves multiple reservations |
| RESERVATION – FOOD_ORDER | 1 : M | Partial – Total | A reservation can have multiple food orders |
| FOOD_ORDER – ORDER_ITEM | 1 : M | Total – Total | Each order contains multiple dishes |
| DISH – ORDER_ITEM | 1 : M | Total – Total | A dish can appear in multiple order items |
| CATEGORY – DISH | 1 : M | Total – Partial | Each dish belongs to one category |
| RESERVATION – BILL | 1 : 1 | Total – Total | Each reservation generates one bill |
| RESTAURANT_TABLE – RESERVATION | 1 : M | Partial – Total | A table can be reserved multiple times |

### Assumptions
1. Each customer is uniquely identified by Customer_ID.
2. A customer can make multiple reservations.
3. Each reservation is assigned to one restaurant table.
4. Customers can make reservations or walk in without prior booking.
5. Each reservation is served by one waiter.
6. A reservation can have multiple food orders.
7. Each food order contains one or more dishes.
8. Each dish belongs to only one category, such as Starter, Main Course, or Dessert.
9. Each reservation generates one bill including food and service charges.
10. A restaurant table can be reserved multiple times at different dates and time slots.
11. Bills can have different payment statuses such as Paid, Pending, or Partially Paid.
12. Table availability is checked before confirming a reservation.

## Instructions for Students

1. Complete **all three scenarios** (A, B, C).  
2. Identify entities, relationships, and attributes for each.  
3. Draw ER diagrams using **draw.io / diagrams.net** or hand-drawn & scanned.  
4. Fill in all tables and assumptions for each scenario.  
5. Export the completed Markdown (with diagrams) as **a single PDF**
