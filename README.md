# Ex03 To-Do List using JavaScript

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>To-Do Application</title>

    <link rel="stylesheet" href="style.css">
</head>

<body>

    <div class="container">

        <h1>My To-Do List</h1>
        <p class="subtitle">Plan your day. Complete your goals. ✨</p>

        <!-- Add Task -->
        <div class="input-box">
            <input
                type="text"
                id="taskInput"
                placeholder="What do you need to do?"
            >

            <button onclick="addTask()">Add Task</button>
        </div>

        <!-- Search -->
        <input
            type="text"
            id="searchInput"
            class="search"
            placeholder="Search tasks..."
            onkeyup="displayTasks()"
        >

        <!-- Filters -->
        <div class="filters">
            <button onclick="setFilter('all')">All</button>
            <button onclick="setFilter('active')">Active</button>
            <button onclick="setFilter('completed')">Completed</button>
        </div>

        <!-- Task Count -->
        <div class="task-header">
            <span id="taskCount">0 tasks</span>

            <button class="clear-btn" onclick="clearCompleted()">
                Clear Completed
            </button>
        </div>

        <!-- Task List -->
        <ul id="taskList"></ul>

        <!-- Empty message -->
        <p id="emptyMessage" class="empty">
            No tasks yet. Add your first task!
        </p>

    </div>

    <script src="script.js"></script>

</body>
</html>
## style.css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;

    min-height: 100vh;

    display: flex;
    justify-content: center;
    align-items: center;

    background: linear-gradient(135deg, #667eea, #764ba2);

    padding: 20px;
}

.container {
    width: 100%;
    max-width: 550px;

    background: white;

    padding: 30px;

    border-radius: 20px;

    box-shadow: 0 15px 40px rgba(0, 0, 0, 0.2);
}

h1 {
    text-align: center;

    font-size: 32px;

    color: #333;

    margin-bottom: 8px;
}

.subtitle {
    text-align: center;

    color: #777;

    margin-bottom: 25px;
}

/* Add task */

.input-box {
    display: flex;

    gap: 10px;

    margin-bottom: 15px;
}

.input-box input {
    flex: 1;

    padding: 14px;

    border: 2px solid #ddd;

    border-radius: 10px;

    font-size: 15px;

    outline: none;
}

.input-box input:focus {
    border-color: #667eea;
}

.input-box button {
    padding: 14px 20px;

    border: none;

    border-radius: 10px;

    background: #667eea;

    color: white;

    font-weight: bold;

    cursor: pointer;
}

.input-box button:hover {
    background: #5568d9;
}

/* Search */

.search {
    width: 100%;

    padding: 13px;

    border: 2px solid #ddd;

    border-radius: 10px;

    outline: none;

    margin-bottom: 15px;
}

.search:focus {
    border-color: #667eea;
}

/* Filters */

.filters {
    display: flex;

    gap: 8px;

    margin-bottom: 20px;
}

.filters button {
    flex: 1;

    padding: 10px;

    border: none;

    border-radius: 8px;

    background: #eee;

    cursor: pointer;

    font-weight: bold;
}

.filters button:hover {
    background: #667eea;

    color: white;
}

/* Task header */

.task-header {
    display: flex;

    justify-content: space-between;

    align-items: center;

    margin-bottom: 15px;

    color: #555;
}

.clear-btn {
    border: none;

    background: transparent;

    color: #e74c3c;

    cursor: pointer;

    font-weight: bold;
}

/* Task */

ul {
    list-style: none;
}

.task {
    display: flex;

    align-items: center;

    justify-content: space-between;

    padding: 13px;

    margin-bottom: 10px;

    background: #f7f7f7;

    border-radius: 10px;

    transition: 0.2s;
}

.task:hover {
    transform: translateY(-2px);

    box-shadow: 0 3px 10px rgba(0, 0, 0, 0.08);
}

.task-left {
    display: flex;

    align-items: center;

    gap: 10px;

    flex: 1;
}

.task-left span {
    word-break: break-word;
}

.task.completed span {
    text-decoration: line-through;

    color: #999;
}

/* Buttons */

.task-buttons {
    display: flex;

    gap: 5px;
}

.task-buttons button {
    border: none;

    padding: 7px 10px;

    border-radius: 7px;

    cursor: pointer;
}

.complete {
    background: #2ecc71;

    color: white;
}

.edit {
    background: #f39c12;

    color: white;
}

.delete {
    background: #e74c3c;

    color: white;
}

/* Empty */

.empty {
    text-align: center;

    color: #999;

    padding: 20px;
}

/* Mobile */

@media (max-width: 600px) {

    .container {
        padding: 20px;
    }

    .input-box {
        flex-direction: column;
    }

    .input-box button {
        width: 100%;
    }

    h1 {
        font-size: 26px;
    }
}
# task.java
public class Task {

    private String taskName;
    private boolean completed;

    public Task(String taskName) {

        this.taskName = taskName;
        this.completed = false;
    }

    public String getTaskName() {

        return taskName;
    }

    public boolean isCompleted() {

        return completed;
    }

    public void completeTask() {

        completed = true;
    }
}
## OUTPUT
<img width="1528" height="732" alt="633210614-87eafd23-269e-4940-bfa3-1bee66308720" src="https://github.com/user-attachments/assets/975add52-5e2b-47c0-bf5e-77b9177a891d" />


## RESULT
The program for creating To-do list using JavaScript is executed successfully.
