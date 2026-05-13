# Ex.No.7 - Develop a Prompt-Based Application Tailored to Personal Needs

### Date:
### Name : Hari Priya M
### Register No: 212224240047
---

# Aim

To develop a prompt-based application using ChatGPT and demonstrate how to create a personal productivity assistant to organize daily tasks, schedule reminders, suggest wellness tips, and answer general queries using natural language interaction.

---

# AI Tools Required

- ChatGPT
- Python
- Tkinter
- VS Code

---

# Explanation

## Prompt

Design a personal productivity assistant that can help manage daily tasks, schedule reminders, suggest wellness tips, and answer general queries. The assistant should interact using natural language and be adaptable to the user’s changing preferences over time.

---

# Procedure

1. Defined the core requirements of a personal productivity assistant.
2. Constructed prompts for managing tasks, reminders, wellness tips, and user queries using ChatGPT.
3. Developed a simple GUI-based application using Python and Tkinter.
4. Simulated natural user interaction through buttons and input fields.
5. Added task management, reminders, wellness suggestions, and summary generation.
6. Displayed outputs and responses based on user interactions.

---

# Python Code

```python
# Personal Productivity Assistant with UI

import tkinter as tk
from tkinter import messagebox

tasks = []

# Add Task
def add_task():

    task = task_entry.get()
    priority = priority_entry.get()

    if task == "" or priority == "":
        messagebox.showwarning("Warning", "Please enter all details")
        return

    task_data = {
        "task": task,
        "priority": priority,
        "completed": False
    }

    tasks.append(task_data)

    output_box.insert(tk.END, f"Task Added: {task}\n")

    task_entry.delete(0, tk.END)
    priority_entry.delete(0, tk.END)

# View Tasks
def view_tasks():

    output_box.insert(tk.END, "\n===== TASK LIST =====\n")

    if len(tasks) == 0:
        output_box.insert(tk.END, "No tasks available\n")
        return

    for i, task in enumerate(tasks):

        status = "Completed" if task["completed"] else "Pending"

        output_box.insert(
            tk.END,
            f"{i+1}. {task['task']} | Priority: {task['priority']} | Status: {status}\n"
        )

# Complete Task
def complete_task():

    try:

        number = int(task_number_entry.get())

        if number >= 1 and number <= len(tasks):

            tasks[number - 1]["completed"] = True

            output_box.insert(
                tk.END,
                f"Task {number} marked as completed\n"
            )

        else:
            messagebox.showerror("Error", "Invalid task number")

    except:
        messagebox.showerror("Error", "Enter valid number")

# Wellness Tip
def wellness_tip():

    output_box.insert(
        tk.END,
        "\nWellness Tip: Drink enough water and take short breaks.\n"
    )

# Assistant Query
def assistant_query():

    query = query_entry.get().lower()

    if "study" in query:
        response = "Use Pomodoro technique and avoid distractions."

    elif "stress" in query:
        response = "Take breaks and practice mindfulness."

    else:
        response = "I am here to improve your productivity."

    output_box.insert(
        tk.END,
        f"\nAssistant Response: {response}\n"
    )

# Daily Summary
def daily_summary():

    total = len(tasks)

    completed = 0

    for task in tasks:

        if task["completed"]:
            completed += 1

    pending = total - completed

    output_box.insert(
        tk.END,
        f"\n===== DAILY SUMMARY =====\n"
    )

    output_box.insert(
        tk.END,
        f"Total Tasks: {total}\nCompleted Tasks: {completed}\nPending Tasks: {pending}\n"
    )

# Main Window
root = tk.Tk()

root.title("Personal Productivity Assistant")

root.geometry("700x600")

# Heading
heading = tk.Label(
    root,
    text="Personal Productivity Assistant",
    font=("Arial", 18, "bold")
)

heading.pack(pady=10)

# Task Input
tk.Label(root, text="Enter Task").pack()

task_entry = tk.Entry(root, width=50)
task_entry.pack()

# Priority Input
tk.Label(root, text="Enter Priority").pack()

priority_entry = tk.Entry(root, width=50)
priority_entry.pack()

# Add Button
add_button = tk.Button(
    root,
    text="Add Task",
    command=add_task,
    bg="lightblue"
)

add_button.pack(pady=5)

# View Button
view_button = tk.Button(
    root,
    text="View Tasks",
    command=view_tasks,
    bg="lightgreen"
)

view_button.pack(pady=5)

# Complete Task
tk.Label(root, text="Task Number").pack()

task_number_entry = tk.Entry(root, width=20)
task_number_entry.pack()

complete_button = tk.Button(
    root,
    text="Complete Task",
    command=complete_task,
    bg="orange"
)

complete_button.pack(pady=5)

# Wellness Button
wellness_button = tk.Button(
    root,
    text="Wellness Tip",
    command=wellness_tip,
    bg="pink"
)

wellness_button.pack(pady=5)

# Query Section
tk.Label(root, text="Ask Query").pack()

query_entry = tk.Entry(root, width=50)
query_entry.pack()

query_button = tk.Button(
    root,
    text="Ask Assistant",
    command=assistant_query,
    bg="yellow"
)

query_button.pack(pady=5)

# Summary Button
summary_button = tk.Button(
    root,
    text="Daily Summary",
    command=daily_summary,
    bg="violet"
)

summary_button.pack(pady=5)

# Output Box
output_box = tk.Text(root, height=15, width=80)

output_box.pack(pady=10)

root.mainloop()
```

---

# EXPECTED OUTPUT

## Personal Productivity Assistant Features

### 1. Daily Task Manager
- Accept tasks using natural language
- Organize tasks by priority
- Display pending and completed tasks
- Generate daily summaries

### 2. Smart Scheduler
- Allow reminder and scheduling support
- Help users organize activities efficiently
- Improve time management

### 3. Wellness Tips Generator
- Suggest hydration reminders
- Recommend screen-time breaks
- Provide healthy productivity tips

### 4. Query Assistant
- Answer productivity-related queries
- Suggest study techniques and focus strategies

---

# Output 

## Main Interface

<img width="700" height="600" alt="image" src="https://github.com/user-attachments/assets/b9efc22d-f90f-4a0b-bf3e-a6d52e51be85" />

## Assistant Query Response

<img width="700" height="600" alt="Screenshot 2026-05-13 135743" src="https://github.com/user-attachments/assets/cbf59b56-14ef-4d9f-9743-72b5b7a1c11c" />

## Daily Summary

<img width="700" height="600" alt="Screenshot 2026-05-13 140033" src="https://github.com/user-attachments/assets/ce292e37-a87b-458c-9607-b0a910e44522" />


---



# Result

The lab exercise resulted in the successful creation of a prototype personal productivity assistant powered by prompt-based interaction. The experiment helped in:
- Understanding prompt engineering techniques
- Developing creativity and problem-solving skills
- Implementing real-world AI-based applications
- Exploring the usefulness of large language models in productivity management
