<script>
    import {supabase} from "../supabase"

    const logout = () => {
        console.log("Log out");
        supabase.auth.signOut();
    }
</script>


<div class="flex justify-end m-0 min-w-full">
    <button 
        class="min-w-fit shadow-sm rounded-lg bg-blue-600
            hover:bg-blue-700 text-white py-2 
            hover:text-black px-4"
        on:click={logout}>Log Out</button>
</div>
