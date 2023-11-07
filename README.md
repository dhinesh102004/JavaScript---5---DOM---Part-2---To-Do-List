# JavaScript---5---DOM---Part-2---To-Do-List
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <style>
        #todoList {
            list-style-type: none;
            padding: 0;
        }

        .task {
            margin-bottom: 10px;
        }

        .deleteBtn {
            cursor: pointer;
            color: red;
            margin-left: 10px;
        }
    </style>
</head>
<body>

    <h2>To-Do List</h2>

    <div>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add Task</button>
    </div>

    <ul id="todoList">

    </ul>

    <script>
        function addTask() {

            const taskInput = document.getElementById('taskInput');
            const taskText = taskInput.value.trim();


            if (taskText !== '') {

                const listItem = document.createElement('li');
                listItem.className = 'task';
                listItem.textContent = taskText;


                const deleteBtn = document.createElement('span');
                deleteBtn.className = 'deleteBtn';
                deleteBtn.textContent = 'Delete';
                deleteBtn.onclick = function () {
                    listItem.parentNode.removeChild(listItem);
                };


                listItem.appendChild(deleteBtn);


                const todoList = document.getElementById('todoList');

                todoList.prepend(listItem);

                taskInput.value = '';
            }
        }
    </script>

</body>
</html>
```
# output
![image](https://github.com/dhinesh102004/JavaScript---5---DOM---Part-2---To-Do-List/assets/142372008/86fe2588-d0b6-4ec3-b7c4-2f5559da588d)
