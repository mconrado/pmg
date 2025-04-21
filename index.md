---
layout: default
---

# Meu Projeto

{% include_relative README.md %}

# Lista de Tarefas Dinâmicas

<ul id="task-list">
</ul>

<script>
    // Função para carregar o estado dos checkboxes
    function loadCheckboxState() {
        const tasks = []; // Nomes das tarefas
        const taskList = document.getElementById('task-list');

        // Adiciona checkboxes dinamicamente
        tasks.forEach(task => {
            const checkbox = document.getElementById(task);
            if (localStorage.getItem(task) === 'true') {
                checkbox.checked = true;
            }
            checkbox.addEventListener('change', () => {
                localStorage.setItem(task, checkbox.checked);
            });
        });
    }

    // Carregar o estado ao iniciar
    window.onload = loadCheckboxState;
</script>
