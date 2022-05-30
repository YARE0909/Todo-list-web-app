<script>
    // @ts-nocheck

    import { loadTodos } from "../stores/todoStore";
    import { supabase } from "../supabase";
    import "../app.css";
    import Auth from "../components/Auth.svelte";
    import {user} from "../stores/authStore.js";
    import Navbar from "../components/Navbar.svelte";
   
    console.log(supabase.auth.user())
    user.set(supabase.auth.user());

    supabase.auth.onAuthStateChange((_, session) => {
        user.set(session?.user)
        if(session?.user){
            loadTodos();
        }
    })
</script>

<div class="bg-gray-900 min-h-screen m-0">
    <div class="container mx-auto my-0 max-w-lg dark:bg-gray-900">
        {#if $user}
            <Navbar/>
            <slot></slot>
        {:else}
            <Auth/>
        {/if}
    </div>
</div>