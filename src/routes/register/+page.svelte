<script>

  import { goto } from "$app/navigation";
  import { PUBLIC_BASE_API } from "$env/static/public";
  import axios from "axios";
    
    const login = async() => {
        try {
            const req = await axios.post(`${PUBLIC_BASE_API}/auth/signin`, {

            })
        }
        catch (e) {
            return e.message
        }
    }

</script>
<div class="flex flex-col justify-center items-center gap-5">
    <h1>Register</h1>
    <div class="flex flex-col items-center">
        <p>FirstName</p>
        <input class="" type="text">
    </div>
    <div class="flex flex-col items-center">
        <p>LastName</p>
        <input class="" type="text">
    </div>
    <div class="flex flex-col items-center">
        <p>Email</p>
        <input class="" type="text">
    </div>
    <div class="flex flex-col items-center">
        <p>Password</p>
        <input class="" type="text">
    </div>
    <button class="border p-2 rounded-md">Register</button>
    <button class="border p-2 rounded-md" onclick={() => {
        goto('/')
    }}>Login👉</button>
</div>