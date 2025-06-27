const tasks = document.querySelectorAll('.task');
const columns = document.querySelectorAll('.column');

tasks.forEach(task => {
  task.addEventListener('dragstart', dragStart);
});

columns.forEach(column => {
  column.addEventListener('dragover', dragOver);
  column.addEventListener('drop', drop);
});

function dragStart(e) {
  e.dataTransfer.setData('text/plain', e.target.innerText);
  e.target.classList.add('dragging');
}

function dragOver(e) {
  e.preventDefault();
}

function drop(e) {
  e.preventDefault();
  const data = e.dataTransfer.getData('text/plain');
  const newTask = document.createElement('div');
  newTask.className = 'task';
  newTask.draggable = true;
  newTask.innerText = data;
  newTask.addEventListener('dragstart', dragStart);
  e.currentTarget.appendChild(newTask);

  document.querySelectorAll('.task.dragging').forEach(t => t.remove());
}
