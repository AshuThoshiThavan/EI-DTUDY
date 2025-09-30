# Human Capital 2025–26 – Coding Exercises

This repo contains my solutions for the **Human Capital coding exercises**.  
I’ve structured the work into two parts:  

1. **Exercise 1** → Demonstrations of six design patterns (Behavioral, Creational, Structural).  
2. **Exercise 2** → A small Java console project: *Astronaut Daily Schedule Organizer*.  

The focus throughout was on **code quality, SOLID principles, design patterns, error handling, and logging** rather than UI.

---

## 🚀 Exercise 1 – Design Patterns

I was asked to come up with six use cases:  

- **2 Behavioral patterns**  
- **2 Creational patterns**  
- **2 Structural patterns**  

### ✅ Behavioral
1. **Observer Pattern** – A subject notifies multiple observers about state changes (e.g., a simple notification system).  
2. **Strategy Pattern** – A calculator that can switch between operations (add, subtract, multiply) at runtime.  

### ✅ Creational
1. **Factory Pattern** – Centralized creation of objects (shapes/tasks) with validation.  
2. **Singleton Pattern** – Ensuring only one instance of a class (used later for the Scheduler too).  

### ✅ Structural
1. **Adapter Pattern** – Making incompatible classes work together (like a plug converter).  
2. **Decorator Pattern** – Dynamically adding new behavior to objects (e.g., extending a notification system).  

📂 Files for Exercise 1:
```
BehavioralPatterns_Observer_Pattern.java
BehavioralPatterns_Strategy_Pattern.java
CreationalPatterns_FactoryPattern.java
CreationalPatterns_Singleton_Pattern.java
StructuralPatterns_Adapter_Pattern.java
StructuralPatterns_Decorator_Pattern.java
```

Each file has a `main` method and can be run individually.

### ▶️ Run Example
```bash
javac BehavioralPatterns_Observer_Pattern.java
java BehavioralPatterns_Observer_Pattern
```

---

## 🛰️ Exercise 2 – Astronaut Daily Schedule Organizer

A console-based Java application that helps astronauts manage their daily tasks.  
The requirements included: CRUD operations, no task overlaps, error handling, logging, and design patterns (Singleton, Factory, Observer).

### ✨ Features
- Add new tasks (description, start/end time, priority).  
- View all tasks sorted by start time.  
- Remove tasks by ID or description.  
- Prevent overlapping/conflicting tasks.  
- Mark tasks as completed.  
- Edit existing task times.  
- Filter tasks by priority.  
- Logs all important events and errors.  

### 🛠️ Design Patterns Used
- **Singleton** → `ScheduleManager` (only one instance manages all tasks).  
- **Factory** → `TaskFactory` (creates validated `Task` objects).  
- **Observer** → `TaskObserver` + `ConsoleNotifier` (notifies about adds, removes, updates, conflicts).  

### 📂 Files
```
AstronautScheduler.java      # Main program (console UI)
Task.java                    # Immutable Task model
TaskFactory.java             # Task creation logic
ScheduleManager.java         # Singleton manager
TaskObserver.java            # Observer interface
ConsoleNotifier.java         # Observer implementation
ConflictException.java       # Custom exception
```

### ▶️ Run Program
```bash
javac *.java
java AstronautScheduler
```

### 💻 Example Interaction
```
> add
Description: Morning Exercise
Start (HH:mm): 07:00
End (HH:mm): 08:00
Priority (High/Medium/Low): High
Task added: 07:00 - 08:00: Morning Exercise [HIGH]

> add
Description: Team Meeting
Start (HH:mm): 09:00
End (HH:mm): 10:00
Priority (High/Medium/Low): Medium
Task added: 09:00 - 10:00: Team Meeting [MEDIUM]

> add
Description: Training Session
Start (HH:mm): 09:30
End (HH:mm): 10:30
Priority (High/Medium/Low): High
CONFLICT: Task 'Training Session' conflicts with existing 'Team Meeting'
ERROR: Task conflicts with existing task: Team Meeting

> view
07:00 - 08:00: Morning Exercise [HIGH]
09:00 - 10:00: Team Meeting [MEDIUM]
```

---

## 📊 Key Focus Areas

- **Code Quality** → SOLID principles, clear separation of concerns.  
- **Design Patterns** → Used appropriately, not just for the sake of it.  
- **Error Handling** → Custom exceptions + graceful user messages.  
- **Logging** → Used `java.util.logging` to track actions and errors.  
- **Maintainability** → Modular structure, easy to extend.  

---

## 🚧 Future Enhancements
- Save/load tasks from a file or DB.  
- Add recurring tasks and reminders.  
- Multiple observers (e.g., file-based logging, alerts).  

---

✨ With this repo, I’ve covered both exercises:  
- Demonstrated design patterns in **Exercise 1**.  
- Built a working console mini-project for **Exercise 2**.  
