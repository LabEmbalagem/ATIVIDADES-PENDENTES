JavaScript
function addTask() {
  const input = document.getElementById('taskInput');
  const taskText = input.value.trim();

  if (taskText === '') {
    alert('Por favor, digite uma atividade!');
    return;
  }

  const ul = document.getElementById('taskList');
  const li = document.createElement('li');

  li.innerHTML = `
    <span onclick="toggleComplete(this)">${taskText}</span>
    <button class="delete-btn" onclick="removeTask(this)">Excluir</button>
  `;

  ul.appendChild(li);
  input.value = '';
}

function toggleComplete(element) {
  element.parentElement.classList.toggle('completed');
}

function removeTask(button) {
  button.parentElement.remove();
}