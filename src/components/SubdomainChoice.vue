<script setup>
import { ref } from 'vue';
const subdomainChoice = ref('no');
</script>
<template>
    <div class="content">
        <h3>Subdomain Choice</h3>
        <div class="subdomain-question">
            <label>Do you want to use a subdomain?</label>
            <div>
                <input type="radio" id="yes" value="yes" v-model="subdomainChoice" />
                <label for="yes">Yes</label>
                <input type="radio" id="no" value="no" v-model="subdomainChoice" />
                <label for="no">No</label>
            </div>
        </div>
        <p class="note"><strong>Note: </strong>: If you choose 'Yes', your FDSA url will have this subdomain added to your FQDN, for example: https://your-fdsa.com/subdomain-selected</p>
        <div class="subdomain-connection" v-if="subdomainChoice === 'yes'">
            <form action="">
                <div class="row">
                    <div class="col">
                        <label for="subdomain">Subdomain</label>
                        <input type="text" id="subdomain" name="subdomain" required />
                    </div>
                </div>
            </form>
        </div>
    </div>
    <div class="buttons">
            <button @click="nextPage">Next</button>
        </div>
</template>
<style scoped>
.content {
    height: 700px;
    padding: 10px 20px;
}
.subdomain-connection {
    margin-top: 80px;
    padding: 0 50px;
    height: 600px;
}
.subdomain-question {
    margin-top: 20px;
    padding: 0 50px;
    display: flex;
    gap: 50px;
}
.content h3 {
    font-size: 20px;
    margin-bottom: 10px;
    text-align: left;
}
.content input[type="radio"] {
    margin-right: 10px;
}
.content input[type="text"] {
    width: 100%;
    padding: 10px;
    margin-top: 5px;
    border-radius: 4px;
    border: 1px solid #ccc;
}
.content input[type="text"]:focus {
    border-color: #007bff;
    outline: none;
}
.content form {
    margin-top: 10px;
}
.buttons {
    display: flex;
    justify-content: flex-end;
    margin-top: 20px;
}
.buttons button {
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
.buttons button:hover {
    background-color: #0056b3;
}
.buttons button:disabled {
    background-color: #ccc;
    cursor: not-allowed;
}
.buttons button:disabled:hover {
    background-color: #ccc;
}
.buttons button:disabled:active {
    background-color: #ccc;
}
.buttons button:active {
    background-color: #0056b3;
}
.note{
    margin-left: 50px;
    font-size: 14px;
    margin-top: 30px;
}
</style>