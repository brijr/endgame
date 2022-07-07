<script>
import { Client, Account } from 'appwrite';

const client = new Client();
const account = new Account(client);

let email = "";
let password = "";
let name = "";

// Init your Web SDK
client
    .setEndpoint('http://161.35.84.116/v1') // Your API Endpoint
    .setProject('62c630547c675cbb918c') // Your project ID
;

// Register User
const newUser = () => {
    account.create('unique()', email, password, name)
        .then(response => {
            console.log(response);
        }, error => {
            console.log(error);
        });
    }

</script>

<form class="text-black">
    <input type="text" bind:value={email}>
    <input type="password" bind:value={password}>
    <input type="text" bind:value={name}>
    <button on:click={newUser}>Register</button>
</form>


