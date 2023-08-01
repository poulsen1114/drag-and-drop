# Task Management Board

This is a simple task management board implemented in HTML, CSS, and JavaScript. It allows users to add, edit, and organize tasks in different columns: Backlog, Progress, Complete, and On Hold.

## How to Use

1. **Add Task**: To add a new task, click on the "+" button in the desired column. A text input box will appear. Enter the task name and click the checkmark button to save it.

2. **Edit Task**: Click on the task name to edit it directly. Press Enter or click outside the task box to save the changes.

3. **Move Task**: To move a task between columns, simply drag and drop it to the desired column.

4. **Delete Task**: To delete a task, remove all text from the task name, and it will be automatically deleted when you click outside the task box.

## Code Structure

The code is organized into different sections and functions:

### HTML Structure

- The task management board is created using a set of `<ul>` elements representing the columns.
- Each column (`backlogList`, `progressList`, `completeList`, and `onHoldList`) is associated with a list of tasks represented as `<li>` elements with the class `drag-item`.

### JavaScript Functions

- `getSavedColumns()` retrieves the tasks from local storage if available or initializes default tasks if not present.
- `updateSavedColumns()` saves the task arrays to local storage.
- `filterArray(array)` removes any `null` items from an array.
- `createItemEl(columnEl, column, item, index)` creates a new `<li>` element for a task and appends it to the corresponding column.
- `updateDOM()` updates the entire task board in the DOM by re-rendering each column and saving the changes to local storage.
- `updateItem(id, column)` updates a task's text content in the corresponding array when edited or deleted.
- `addToColumn(column)` adds a new task to the selected column.
- `showInputBox(column)` and `hideInputBox(column)` control the visibility of the input box for adding new tasks in a column.
- `rebuildArrays()` uses the `map` function to rebuild the task arrays for each column from the DOM.
- `drag(e)` is called when a task starts being dragged to set the dragged item.
- `allowDrop(e)` and `dragEnter(column)` are used to handle drag and drop events.
- `drop(e)` is called when a task is dropped into a column, updating the arrays and the DOM.

### Initialization

- `updatedOnLoad` is used to ensure `getSavedColumns()` is called only once on page load.
- The `listArrays` store the task arrays for each column (`backlogListArray`, `progressListArray`, `completeListArray`, and `onHoldListArray`).
- The task arrays are initialized either from local storage or with default values.
- The `updateDOM()` function is called to initially populate the task board.

## Browser Compatibility

This task management board should work in most modern web browsers that support ES6 features, drag-and-drop functionality, and local storage.