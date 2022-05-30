<script>
// @ts-nocheck

    import { supabase } from "../supabase.js";

    let loading = false;
    let email;

    const handleLogin = async () => {
        try {
            loading = true;
            console.log(email);           
            const {error} = await supabase.auth.signIn({email});

            if(error) throw error;
            alert('Check your email for the login link!')
        } catch (error) {
            console.error(err)
            alert(error.error_description || error.message)
        }finally{
            loading = false;
        }
    }
</script>

<h1 class="text-2xl font-bold text-center
          text-white md:text-3xl m-0">Log In</h1>
        
<p class="text-white text-centre mt-2 p-2">Sign in via magic link with your email below</p>

<form on:submit|preventDefault={handleLogin}>
    <div class="flex flex-col text-sm mb-2 p-2">
        <label class="font-bold mb-2 text-white"
               for="email">Email</label>
        <input class="appearance-none shadow-sm border border-gray-400 p-2
                     focus:outline-none focus:border-gray-500 rounded-lg
                     bg-gray-800 text-white" name="email" type="email"
                     placeholder="Your email" bind:value={email}>
    </div>
    <button class="p-2 shadow-sm bg-blue-600 hover:bg-blue-700 
                  text-white hover:text-black rounded-lg
                  px-4 py-2 w-full" type="submit">Login</button>
</form>