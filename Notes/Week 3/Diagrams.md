- A **diagram** is a **visual representation** of a system, process, or concept.
- It helps communicate structure, behavior, and relationships **without diving into code**.
- Think of diagrams as **blueprints** for your application—just like architects use blueprints before building a house.

### Why Use UML and Class Diagrams?

- 🔍 **Plan Before Coding**: Easier to visualize the system.
- 🤝 **Team Communication**: Everyone sees the big picture. 
- 📚 **Documentation**: Explains your system to future developers.
- ✅ **Problem Solving**: Makes it easier to debug structure-level design issues.

#### **UML (Unified Modeling Language) Diagram** 
UML provides a set of **diagram types** that developers, architects, and business analysts use to.
- Model the **structure** of systems (what things are)
- Model the **behavior** of systems (how things work)
- Explain **interactions** between different parts
A **UML (Unified Modeling Language) Diagram** is a visual way to **design, describe, and understand software systems**. UML diagrams help you plan and communicate how different parts of your system behave or interact **before writing code**.

In a Banking App 

| User          |
| ------------- |
| addMoney()    |
| viewBalance() |
| login()       |
- This tells your team what features the user needs **without touching code**.

### **Class Diagram**
- A **Class Diagram** is a type of UML diagram that shows the **structure of classes** in your system.
- [?] It will Give us
- What **classes** exist
- What **properties/attributes** they have
- What **methods/functions** they perform
- How classes are **related** to each other (e.g., inheritance)

If we create a school

| People                      |
| --------------------------- |
| User                        |
| Students(Inherit from User) |
| Teacher (Inherit from User) |

| User        | User         | User           |
| ----------- | ------------ | -------------- |
| name:String | name:String  | name:String    |
| age:number  | age:number   | age:number     |
|             | grade:string | subject:string |

![[db.png]]
the dashed line and arrow mean `userService` **depends on** `axios` (or: `userService` **uses** methods from `axios`)

### **ER Diagram (Entity-Relationship Diagram)**
- Purpose: Represents the **data model** of a system.
- Focuses on: Entities (tables), relationships, and attributes.
- Used in: Database design.

### **Flow Chart**
- Purpose: Represents a **step-by-step process or algorithm**.
- activities had a custom shapes like Ovals (Start/End), Rectangles (Processes), Diamonds (Decisions), Arrows (Flow).
![[Pasted image 20250408175359.png | 400]]

### **Use Case Diagram**
- **Used for**: Showing **who** uses the system and **what they can do**.

**In a Library App:**
- A **User** can: borrow books, return books, search catalog.
- A **Librarian** can: add/remove books.

| User        | Librarian      |
| ----------- | -------------- |
| take books  | Add Book       |
| returnBooks | Mark as return |
| searchBooks | Remove book    |

### **Sequence Diagram**
- **Used for**: Showing how **objects interact over time**
In a Login system:
- User → Login Page → AuthService → Database

>User --> LoginPage: enter credentials
LoginPage --> AuthService: validate credentials
AuthService --> Database: query user
Database --> AuthService: return user
AuthService --> LoginPage: success/failure

### **Activity Diagram**
- **Used for**: Showing the **flow of actions** or logic, like a flowchart.
> [!Work] WorkFlow
> Start
 ↓
Fill Registration Form
 ↓
Validate Inputs
 → [Invalid] → Show Error → End
 ↓
Send Confirmation Email
 ↓
End


### **State Diagram**
- **Used for**: Showing **different states** an object can be in, and how it transitions between them.
> [!work]
> [Created] → [In Progress] → [Completed]
                   ↑
              [Reopened]

### **Component Diagram**
- **Used for**: Showing high-level **components/modules** of a system and how they interact.
> [!Work]
> [Frontend App] → [API Gateway] → [Auth Service] ->[Database Service]

### **Deployment Diagram**
- **Used for**: Showing how your system is **physically deployed** (servers, databases, devices, etc.)
>[!work]
>[Client Machine] -> Web Server] ———> [Application Server] ->  [Database Server]

### 

function diagram
1. group all classes
2. ER diagrsam