'''A Task Management System using python which gives user an option to view all tasks on portal,view tasks created by them.It also give user option to create,edit and delete tasks on basis of ownership'''
# Implementation-of-task-management-system-using-python
# -*- coding: utf-8 -*-
"""Implementation of task management system using python.ipynb

Original file is located at
    https://colab.research.google.com/drive/1sHhPOlSxs2ky7BKH2ERDL6ThAsilNjnD

# Implementation of task management system using python
"""

class Task:
    def __init__(self, name, description, due_date):
        self.name = name
        self.description = description
        self.due_date = due_date
        self.status = "Pending"

    def update_status(self, new_status):
        self.status = new_status

    def get_details(self):
        return f"Task: {self.name}\nDescription: {self.description}\nDue Date: {self.due_date}\nStatus: {self.status}"

class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)

    def remove_task(self, task):
        self.tasks.remove(task)

    def update_task_status(self, task, new_status):
        task.update_status(new_status)

    def display_tasks(self):
        for task in self.tasks:
            print(task.get_details())

# Create task instances
task1 = Task("Complete project", "Finish coding and testing", "2023-06-30")
task2 = Task("Prepare presentation", "Create slides and rehearse", "2023-06-25")

# Create task manager instance
task_manager = TaskManager()

# Add tasks to the task manager
task_manager.add_task(task1)
task_manager.add_task(task2)

# Update task status
task_manager.update_task_status(task1, "In Progress")

# Display tasks
task_manager.display_tasks()
