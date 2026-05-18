# ER Diagram Workshop – Submission Template

## Objective
To understand and apply ER modeling concepts by creating ER diagrams for real-world applications.

## Purpose
Gain hands-on experience in designing ER diagrams that represent database structure including entities, relationships, attributes, and constraints.



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
<img width="1196" height="888" alt="Screenshot 2026-02-05 154450" src="https://github.com/user-attachments/assets/d5e534a5-1617-4fe3-90df-518653315079" />

### Entities and Attributes

| Entity            | Attributes (PK, FK)                                                       | Notes                                           |
| ----------------- | ------------------------------------------------------------------------- | ----------------------------------------------- |
| Member            | MemberID (PK), Name, Address, Phone                                       | Each member has a unique ID                     |
| Book              | BookID (PK), ISBN, Title, Author, Category                                | A book can be borrowed multiple times           |
| Loan              | LoanID (PK), LoanDate, ReturnDate, FineAmount, MemberID (FK), BookID (FK) | Resolves M:N between Member and Book            |
| Event             | EventID (PK), Title, Description, Date, Time, RoomID (FK)                 | Each event occurs in one room                   |
| EventRegistration | RegistrationID (PK), RegistrationDate, MemberID (FK), EventID (FK)        | Resolves M:N between Member and Event           |
| Speaker           | SpeakerID (PK), Name, Expertise                                           | Each speaker may participate in multiple events |
| Room              | RoomID (PK), RoomName, Type, Capacity                                     | Each event is assigned to one room              |

### Relationships and Constraints

| Relationship                       | Cardinality                          | Participation                   | Notes                                 |
| ---------------------------------- | ------------------------------------ | ------------------------------- | ------------------------------------- |
| Member – Loan                      | 1:N                                  | Total on Loan side              | Each loan belongs to one member       |
| Loan – Book                        | N:1                                  | Total on Loan side              | Each loan involves one book           |
| Member – Book (via Loan)           | M:N (resolved via Loan)              | Total via Loan                  | Many members can borrow many books    |
| Member – EventRegistration – Event | M:N (resolved via EventRegistration) | Total on EventRegistration side | Members register for multiple events  |
| Event – Speaker                    | M:N                                  | Partial on both sides           | Events can have multiple speakers     |
| Event – Room                       | 1:N                                  | Total on Event side             | Each event occurs in exactly one room |
| Room – Event                       | 1:N                                  | Partial on Room side            | A room can host multiple events       |

### Assumptions
- Each book can be borrowed by one member at a time.

- Each event must have at least one speaker and one booked room.

---
### Result 
Hence, the concepts of ER diagrams are understood and applied by creating an ER diagram for a real-world City Library Event & Book Lending System.


