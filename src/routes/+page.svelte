<script>

  import { goto } from "$app/navigation";
  import { PUBLIC_BASE_API } from "$env/static/public";
  import axios from "axios";

  let email = $state()
  let password = $state()
  const login = async() => {
        try {
            const req = await axios.post(`${PUBLIC_BASE_API}/auth/signin`, {
                email,
                password
            })

            if (req.status == 200) {
                goto('/home')
            }
            else {
                alert('something was wrong')
            }
        }
        catch (e) {
            return e.message
        }
    }

</script>
<div class="flex flex-col justify-center items-center gap-5">
    <h1>Login</h1>
    <div class="flex flex-col items-center">
        <p>Email</p>
        <input class="" type="email" bind:value={email}>
    </div>
    <div class="flex flex-col items-center">
        <p>Password</p>
        <input class="" type="password" bind:value={password}>
    </div>
    <button class="border p-2 rounded-md" onclick={() => {
        login()
    }}>Login</button>
    <button class="border p-2 rounded-md" onclick={() => {
        goto('/register')
    }}>Register👉</button>
</div>