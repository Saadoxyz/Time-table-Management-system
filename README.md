
# 🗓️ Timetable Scheduling System

![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge\&logo=c%2B%2B\&logoColor=white)
![CSV](https://img.shields.io/badge/CSV-Supported-informational?style=for-the-badge\&logo=filezilla\&logoColor=white\&color=orange)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Stable-green?style=for-the-badge)

---

## 📌 Overview

The **Timetable Scheduling System** is a C++ application designed to help **universities and academic institutions** manage, adjust, and resolve conflicts in their class schedules. It supports **loading**, **editing**, **conflict checking**, **automatic adjustment**, and **backup** of timetables from and to `.CSV` files.

---

## 🧠 Key Features

* ✅ **Load timetable data from CSV**
* 🔄 **Auto-adjust schedule to avoid teacher conflicts and consecutive labs**
* ✏️ **Manually update or edit class entries**
* 🔍 **Search classes by teacher name**
* 💾 **Save/backup adjusted timetable**
* ⚠️ **Conflict detection** using teacher-specific structures
* 📊 **Supports Excel-style output via CSV**

---

## 🛠️ Technologies Used

| Category        | Details                                 |
| --------------- | --------------------------------------- |
| Language        | C++                                     |
| File Format     | `.csv` (Comma-Separated)                |
| Data Structures | Circular Doubly Linked List, Structures |
| IDE Recommended | Code::Blocks / Visual Studio / VSCode   |
| OS Support      | Windows / Linux                         |

---

## 🧩 Data Structures Used

### 1. `Node`

Used to represent a subject entry in the timetable:

```cpp
struct Node {
    string T_Name;
    string Subject;
    int Room_no;
    bool HasLab;
    int CreditHour;
    int OriginalCreditHour;
    Node* next;
    Node* prev;
};
```

### 2. `TeacherConflict`

Stores conflict day and slot for teachers.

```cpp
struct TeacherConflict {
    string T_Name;
    int day;
    int slot;
};
```

### 3. `TeacherSchedule`

Stores a teacher’s schedule and conflict count.

```cpp
struct TeacherSchedule {
    string T_Name;
    TeacherConflict conflicts[Day * Slot];
    int count;
};
```

---

## 🔧 Functionalities

| Function                             | Description                                     |
| ------------------------------------ | ----------------------------------------------- |
| `insertTeacherConflict`              | Registers a teacher’s conflict for a slot/day.  |
| `hasTeacherConflict`                 | Checks if a conflict exists.                    |
| `insertNode`                         | Adds an entry to the circular list.             |
| `loadDataFromCSV`                    | Loads timetable data from `.csv`.               |
| `shuffleListAvoidingConsecutiveLabs` | Prevents assigning back-to-back lab sessions.   |
| `auto_adjust`                        | Automatically assigns slots avoiding conflicts. |
| `editTimetable`                      | Allows manual update of the schedule.           |
| `saveAdjustedTimetableToCSV`         | Saves the adjusted timetable.                   |
| `searchTeacherClassesInFile`         | Finds all classes taught by a specific teacher. |

---

## 🖥️ How It Works

### 📥 Load Timetable

Load the original `.csv` timetable which includes:

```
Teacher Name, Subject, Room Number, Has Lab (1/0), Credit Hours
```

### 🧠 Automatic Adjustment

* Avoids assigning **consecutive labs**.
* Prevents assigning a teacher to **multiple classes in the same time slot**.

### ✍️ Manual Editing

Update subject, room, or lab status via CLI interface.

### 🔍 Teacher Search

Easily find which teacher is teaching **what**, **when**, and **where**.

### 💾 Backup & Export

Saves adjusted timetable as:

```
Section, Day, Slot, Subject
```

---

## 📂 File Structure

```
|-- timetable.cpp
|-- teachers.csv
|-- adjusted_schedule.csv
|-- backup_schedule.csv
```

---

## 🧪 Sample Usage

```bash
> Load Timetable
> Search by Teacher Name
> Edit Day 3, Slot 2
> Save Adjusted Timetable
```

---

## 🧾 Menu System

1. 🔄 **Backup Timetable**
2. 🔍 **Search for Specific Teacher**
3. ✏️ **Edit / Update Timetable**
4. ❌ **Exit**

---

## 🔚 Conclusion

This project demonstrates an efficient use of **C++ data structures** for solving real-world **academic scheduling** problems. With **conflict resolution**, **lab control**, and **manual override**, it balances automation and user control.

---

## 👨‍💻 Author

**Muhammad Saad Khan**

* 💼 Computer Science Student
* 🛠 Focused on System Software, Networking, and Timetable Management Tools
* 📬 [saado652004@gmail.com](mailto:saado652004@gmail.com)

---

## 🌟 Give a Star

If you found this helpful, feel free to ⭐ the repo and share it!

---

