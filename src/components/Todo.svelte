<script>
// @ts-nocheck

    import { deleteTodo, toggleTodoCompleted } from "../stores/todoStore";
    export let todo;
</script>

<li class="bg-gray-dark flex items-center py-2 px4">
    <input name="completed" type="checkbox" checked={todo.completed}
           on:change={() => toggleTodoCompleted(todo.id)}
           class="mr-2 form-checkbox h-5 w-5"/>
           <span class={`flex-1 text-white ${todo.completed ? 'line-through': ''}`}>{todo.text}</span>
           <button
           type="button"
           class="text-sm bg-gray-500 hover:bg-red-600 text-white
                py-1 px-2 rounded focus:outline-none focus:shadow-outline"
           on:click={() => deleteTodo(todo.id)}>Delete</button>    
</li>