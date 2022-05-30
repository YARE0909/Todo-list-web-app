<script>
    let todo = '';
    import {addTodo} from "../stores/todoStore.js"
    const handleSubmit = () => {
        addTodo(todo);
        todo = '';
        console.log("Submitting")
    }
</script>

<form class="my-6" on:submit|preventDefault={handleSubmit}>
    <div class="flex flex-col text-sm mb-2">
        <label class ="font-bold mb-2 text-white" 
                       for="todo">Todo</label>
        <input class="appearance-none shadow-sm border 
                    border-gray-400 p-2 focus:outline-none 
                    focus:border-gray-500 rounded-lg
                    bg-gray-800 text-white" 
                    type="text" name="todo" placeholder="Watcha gotta do?"
                    bind:value={todo}/>
    </div>
    <button class="w-full shadow-sm rounded bg-blue-600
                   hover:bg-blue-700 text-white py-2 
                    hover:text-black px-4" 
                    type="submit">Add</button>
</form>