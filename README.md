# -Smart-School-Timetable-Generator.


A full-stack algorithmic solution designed to automate the complex process of scheduling school classes. This system resolves time-conflicts, manages teacher availability, and handles complex grouping logic (like parallel language classes) to generate a conflict-free timetable for an entire academic year.

🛠️ Tech Stack

Backend: Python, Django, Django REST Framework (DRF)
Database: PostgreSQL (Relationally Optimized)
Frontend: React.js, Tailwind CSS ,redux
Architecture: RESTful API, Service-Oriented Logic



🚀 Key Features & Architectural Decisions
1. Intelligent Scheduling Algorithm
Implemented a Constraint Satisfaction Algorithm to generate timetables automatically.

Conflict Detection: Prevents "Double Booking" (e.g., a teacher assigned to two classes simultaneously or a class having two subjects at once).

Heuristic Optimization: Prioritizes hard constraints (e.g., Math must be before lunch) and soft constraints (teacher preferences).

2. Advanced "Clubbing" & Parallel Scheduling
Solved the "Split Class" problem where students from different divisions (e.g., 10-A and 10-B) mix for specific subjects like Second Languages (Arabic/Malayalam).

Engineered a ParallelGroup data structure that locks multiple workloads together, forcing the algorithm to schedule them in the exact same time slot across different classes.


3. Dynamic Teacher Availability (Blocking)
Created a flexible Blocking System allowing teachers to restrict availability based on real-world needs (e.g., "No classes on Friday last period due to train timings").

Supports both specific slots (Friday Period 7) and recurring patterns (Every Monday Morning).

4. Scalable Database Design
UUIDs: Used universally unique identifiers for all primary keys to ensure security and easy data migration.

Normalized Schema: Designed efficient many-to-many relationships for Workloads and Schedules to minimize data redundancy.

Atomic Transactions: Implemented transaction.atomic() for bulk operations (like bulk assigning subjects) to ensure database integrity.

🔗 API Architecture Highlights
Bulk Assignments: Custom API endpoints to handle bulk creation of class workloads, reducing frontend-backend network chatter.

Constraint Validation: Serializer-level validation to ensure data integrity before it ever reaches the database.

Separation of Concerns: "Workload" (What needs to be taught) is strictly separated from "Schedule" (When it is taught), allowing for easy rescheduling without data loss.

💡 The Problem It Solves
Manual timetable creation for schools is error-prone and time-consuming. A single change (like a teacher leaving) often requires re-doing the entire schedule. This application turns a 2-week manual task into a 5-second automated generation, ensuring 100% conflict-free schedules while respecting teacher comfort and pedagogical rules.

👨‍💻 My Role
Designed the Entity Relationship Diagram (ERD) and Database Schema.

Built the REST API with Django Rest Framework.

Implemented the Scheduling Logic and Conflict Detection systems.

Developed the frontend interfaces for managing complex data associations.
