<script>
// @ts-nocheck

    import TodoForm from "../components/TodoForm.svelte";
    import Todo from "../components/Todo.svelte";
    import {todos} from "../stores/todoStore";

</script>
<body style="background-color: #1e2124">
    <main> 
        <h1 class="text-2xl font-bold text-center text-white font-Roboto rounded-lg md:text-3xl">TODO List</h1>
        <TodoForm/>
        {#each $todos as todo }
            <Todo todo={todo} index={todos.id}/>
        {/each}
    </main>
</body>

