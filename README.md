# Python_PQ1
task_list = []

def add(task):
    task_list.append(task)
    print("Task " + task + " added successfully.")

def view():
    if not task_list:
        print("No task to display.")
    else:
        print("Tasks: ")
        i = 1
        for task in task_list:
            print(str(i) + ". " + task)
            i += 1

def complete(task_index):
    if 1 <= task_index <= len(task_list):
        complete = task_list[task_index - 1]
        del task_list[task_index - 1]
        print("Task " + complete + " marked as completed.")
    else:
        print("Invalid task index.")

while (True):
    print("\nTo-Do List Menu: ")
    print("1. Add a task")
    print("2. View a task")
    print("3. mark test as completed")
    print("4. quit")

    choice = input("Enter your choice (1,2,3,4): ")

    if (choice == "1"):
        task = input("Enter the task: ")
        add(task)
    elif (choice == "2"):
        view()
    elif (choice == "3"):
        task_index = int(input("Enter the index of the task to be marked as complete: "))
        complete(task_index)
    elif (choice == "4"):
        print("**** EXIT ****")
        break
    else: 
        print("invalid choice")
