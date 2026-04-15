# AI-Based_Time_Table_Generator


# AI-Based Time Table Generator

## 📌 Project Overview

The **AI-Based Time Table Generator** is a simple Python project designed to automatically create a weekly timetable using basic logic and randomness. It eliminates the manual effort required in scheduling by dynamically assigning subjects across multiple days and periods.

This project demonstrates how foundational programming and logic can simulate intelligent decision-making systems, making it a beginner-friendly introduction to automation concepts in AI.

---

## 🎯 Objectives

* Automate timetable generation
* Avoid repetitive subject allocation patterns
* Ensure fair distribution of subjects across days
* Provide a simple and readable output format

---

## 🛠️ Technologies Used

* **Programming Language:** Python
* **Core Concepts:**

  * Lists and Dictionaries
  * Randomization (`random` module)
  * Functions
  * Basic algorithmic logic

---

## ⚙️ System Design

### Inputs:

* Days of the week (Monday to Friday)
* List of subjects
* Number of periods per day

### Processing:

* Shuffle subjects randomly for each day
* Ensure enough subjects are available for all periods
* Assign subjects to each period per day

### Output:

* A structured timetable printed in the console

---

## 🧠 Algorithm Explanation

1. Define a list of days and subjects.
2. Loop through each day:

   * Copy and shuffle the subject list.
   * If subjects are fewer than required periods, duplicate the list.
   * Assign subjects to each period.
3. Store results in a dictionary.
4. Print the timetable in a readable format.

---

## 💻 Code Implementation

```python
import random

# Configuration
days = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"]
subjects = ["Math", "Physics", "Chemistry", "English", "Computer", "Biology"]
periods_per_day = 5

# Function to generate timetable
def generate_timetable():
    timetable = {}

    for day in days:
        daily_subjects = subjects.copy()
        random.shuffle(daily_subjects)

        if len(daily_subjects) < periods_per_day:
            daily_subjects *= 2

        timetable[day] = daily_subjects[:periods_per_day]

    return timetable

# Function to display timetable
def print_timetable(timetable):
    print("\nGenerated Time Table:\n")

    for day, subjects in timetable.items():
        print(day + ":")
        for i, subject in enumerate(subjects):
            print(f"  Period {i+1}: {subject}")
        print()

# Run
timetable = generate_timetable()
print_timetable(timetable)
```

---

## 📊 Sample Output

```
Generated Time Table:

Monday:
  Period 1: Physics
  Period 2: Math
  Period 3: English
  Period 4: Biology
  Period 5: Computer
...
```

---

## ✅ Features

* Simple and easy to understand
* Fully automated timetable generation
* Randomized scheduling
* Lightweight and fast execution

---

## ⚠️ Limitations

* No constraint handling (e.g., teacher availability, room allocation)
* Subjects may repeat unevenly across the week
* Not optimized for real-world scheduling complexity

---

## 🚀 Future Enhancements

* Add constraints (teacher availability, subject priority)
* Use AI/ML algorithms for optimized scheduling
* Export timetable to file formats (PDF, Excel)
* Build a GUI or web-based interface
* Add database integration

---

## 📌 Conclusion

This project serves as a foundational model for automated scheduling systems. While simple, it provides insight into how logic-based systems can mimic intelligent behavior, forming the basis for more advanced AI-driven solutions.

---

## 📄 License

This project is open-source and free to use for educational purposes.
