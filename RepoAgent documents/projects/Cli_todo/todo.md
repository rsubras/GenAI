## FunctionDef todo(ctx)
**todo**: The function of todo is to read data from a file named todo.txt and transfer it to the context object in a CLI Todo App.

**parameters**: 
· ctx: The context object used to store and transfer data.

**Code Description**: 
The todo function reads the content of the todo.txt file, where the first line contains the latest ID, and the subsequent lines contain tasks and their corresponding IDs. It then transfers this data to the context object by storing the latest ID in the 'LATEST' key and creating a dictionary of tasks with their IDs in the 'TASKS' key.

**Note**: 
Ensure that the todo.txt file exists and is correctly formatted with the latest ID on the first line and tasks with IDs separated by '```' on the following lines.
## FunctionDef tasks(ctx)
**tasks**: The function of tasks is to display tasks stored in the context.

**parameters**:
- ctx: The context object containing the tasks to be displayed.

**Code Description**:
The tasks function first checks if there are any tasks stored in the context object. If tasks are found, it iterates through each task and prints them along with their corresponding IDs. Each task is displayed in a formatted manner with a bullet point before the task description and the task ID in parentheses. If no tasks are found in the context, a message prompting the user to add tasks is displayed.

**Note**:
- Ensure that the ctx object passed to the function contains the 'TASKS' key with the tasks to be displayed.
## FunctionDef add(ctx, add_task)
**add**: The function of add is to add a task to the task list and update the todo.txt file with the new task.

**parameters**:
- ctx: The context object containing the task list and the latest task ID.
- add_task: The task to be added to the list.

**Code Description**:
The add function first checks if a task is provided. If a task is provided, it adds the task to the task list in the context object using the latest task ID as the key. It then prints a message indicating the successful addition of the task with its ID. 

Next, the function updates the todo.txt file by writing the current index (latest task ID + 1) and all tasks with their respective IDs in the format "task ID```task". This information is written to the file, overwriting any existing content.

**Note**:
- Ensure that the context object (ctx) contains the 'TASKS' dictionary and 'LATEST' key for the function to work correctly.
- The todo.txt file will be created or overwritten in the current directory where the script is executed.
## FunctionDef done(ctx, fin_taskid)
**done**: The function of done is to delete a task by its ID.

**parameters**:
- ctx: The context object containing the task list and other information.
- fin_taskid: The ID of the task to be deleted.

**Code Description**:
The function first checks if the task with the provided ID exists in the task list stored in the context object. If the task is found, it is deleted from the task list. The function then prints a message indicating the task has been finished and removed. 

If there are remaining tasks in the list, the function updates the todo.txt file with the current index and the tasks with their IDs separated by " ``` ". If the task list is empty after deletion, the function resets the ID tracker to 0 in the todo.txt file.

**Note**:
- Ensure the task ID provided for deletion exists in the task list.
- The function updates the todo.txt file with the latest task information after deletion.
