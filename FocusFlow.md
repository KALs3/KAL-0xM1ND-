so i had the idea of building a personal project it's a mobile app to be specific the whole idea **is it's a productivity app** that he**lps you get things done and keep you motivated** i still didn't specify what tech stack to use but generally I'm still thinking about the main features that should be there so i thought of **having a todo list and a pomodoro timer with some streak system and analytics that shows you your progress** 

**MVP (minimal viable product )** : 

features : 
✅ **To-Do List** – Track tasks  
✅ **Pomodoro Timer** – Time management  
✅ **Streak System** – Encourage consistency  
✅ **Basic Analytics** – Show progress

# Tech Stack

### **Recommended Stack for The App**

| Feature                | Recommended Tool              |
| ---------------------- | ----------------------------- |
| **UI Framework**       | Flutter (Material Design)     |
| **Local Database**     | SQLite (`sqflite`) or Hive    |
| **State Management**   | Provider or Riverpod          |
| **Notifications**      | `flutter_local_notifications` |
| **Reminders & Alarms** | `android_alarm_manager_plus`  |
| **Charts & Analytics** | `fl_chart`                    |
| **Animations**         | `Lottie` or `rive`            |
| **Backup/Export**      | `SharePlus` or File Picker    |
# the **data structure** (how tasks, habits, streaks are stored)?
#### **Task Model (To-Do List)**

```dart
class Task {
  int id;                // Unique task ID
  String title;          // Task description
  String? description;   // Optional details
  DateTime? dueDate;     // Deadline (nullable)
  bool isCompleted;      // Task status
  int priority;          // 1 = Low, 2 = Medium, 3 = High
  
  Task({
    required this.id,
    required this.title,
    this.description,
    this.dueDate,
    this.isCompleted = false,
    this.priority = 2, 
  });
}


```

📌 **Why?**

- Keeps tasks simple but allows extra info like descriptions & due dates.
- Priority helps with organizing tasks.

---

#### **⏳ Pomodoro Model (Focus Timer)**


```dart
class PomodoroSession {
  int id;
  int taskId;        // Link to a Task (Foreign Key in SQLite)
  int duration;      // Total minutes (e.g., 25)
  int completedCycles; // Number of Pomodoro cycles finished
  DateTime timestamp; // When the session was done

  PomodoroSession({
    required this.id,
    required this.taskId,
    required this.duration,
    this.completedCycles = 0,
    required this.timestamp,
  });
}


```
📌 **Why?**

- Tracks how many Pomodoro cycles were completed for a task.
- Useful for **analytics** (e.g., "Which tasks take the most time?").

---

#### **🔥 Habit Model (Habit Tracker)**

```dart
class Habit {
  int id;
  String name;       // Name of habit (e.g., "Exercise")
  int frequency;     // How often (1 = Daily, 2 = Weekly, etc.)
  int streak;        // Current streak count
  DateTime lastUpdated; // Last time habit was marked done

  Habit({
    required this.id,
    required this.name,
    required this.frequency,
    this.streak = 0,
    required this.lastUpdated,
  });
}

```

📌 **Why?**

- Streak system to motivate users.
- Frequency helps with tracking daily vs. weekly habits.

---

#### **📊 Analytics Model**

```dart
class Analytics {
  int id;
  int totalTasksCompleted;
  int totalPomodoroMinutes;
  int bestStreak;
  DateTime lastUpdated;

  Analytics({
    required this.id,
    this.totalTasksCompleted = 0,
    this.totalPomodoroMinutes = 0,
    this.bestStreak = 0,
    required this.lastUpdated,
  });
}

```
📌 **Why?**

- Tracks productivity trends over time.
- Can be used for progress graphs and insights.


# Application design and UI

1️⃣ **Home Screen** → Overview of tasks, habits, and progress.  
2️⃣ **To-Do List Screen** → Add, edit, and complete tasks.  
3️⃣ **Pomodoro Timer Screen** → Start, pause, and track focus sessions.  
4️⃣ **Habit Tracker Screen** → Mark habits as done, view streaks.  
5️⃣ **Analytics Screen** → Show streaks, completed tasks, and Pomodoro time.  
6️⃣ **Settings Screen** → Theme toggle (light/dark), notifications, etc.


# App design and UI
this is not meant to be used as the full sketch to the app but more as A reference to how the elements of the app should be represented
and not meant to be taken as a form of copy pasting designs 


![[Pasted image 20250322210027.png]]

![[Pasted image 20250322205954.png]]

# Color scheme
- **Primary:** 🟢 Teal Green (#14B8A6)
- **Accent:** ⚪ Soft White (#E5E7EB)
- **Background:** ⚫ Dark Gray (#18181B) (for dark mode)
- **Light Text:** 🔵 Deep Navy Blue (#1E293B)

