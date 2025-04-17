<script setup>
import { ref } from 'vue';
const externalDb = ref('no');
</script>
<template>
    <div class="content">
        <h3>External Database</h3>
        <div class="db-question">
            <label>Do you want to use an external PostgreSQL database?</label>
            <div>
                <input type="radio" id="yes" value="yes" v-model="externalDb" />
                <label for="yes">Yes</label>
                <input type="radio" id="no" value="no" v-model="externalDb" />
                <label for="no">No</label>
            </div>
        </div>

        <div class="db-connection" v-if="externalDb === 'yes'">
            <form action="">
                <div class="row">
                    <div class="col">
                        <label for="db-host">Database Host</label>
                        <input type="text" id="db-host" name="db-host" required />
                    </div>
                    <div class="col">
                        <label for="db-port">Database Name</label>
                        <input type="text" id="db-name" name="db-port" required />
                    </div>
                </div>
                <div class="row">
                    <div class="col">
                        <label for="db-user">Database User</label>
                        <input type="text" id="db-user" name="db-user" required />
                    </div>
                    <div class="col">
                        <label for="db-password">Database Password</label>
                        <input type="password" id="db-password" name="db-password" required />
                    </div>
                </div>
            </form>
        </div>
    </div>
    <div class="buttons">
        <button>Next</button>
    </div>
</template>
<style scoped>
.content {
    height: 700px;
    padding: 10px 20px;
}
.db-connection {
    margin-top: 80px;
    padding: 0 50px;
}

.content h3 {
    font-size: 20px;
    margin-bottom: 10px;
    text-align: left;
}

.content input[type="radio"] {
    margin-right: 5px;
    color: #000;
}


.content input[type="text"],
.content input[type="password"] {
    width: 100%;
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

.content input[type="text"]:focus,
.content input[type="password"]:focus {
    border-color: #007bff;
    outline: none;
}

.content form {
    margin-top: 10px;
}

.content form label {
    font-weight: bold;
    text-align: left;
}

.content form input[type="text"],
.content form input[type="password"] {
    width: calc(100% - 16px);
    padding: 8px;
    margin-bottom: 10px;
    border-radius: 4px;
    border: 1px solid #ccc;
}

span {
    font-size: 14px;
    color: #555;
    text-align: left;
    font-size: 18px;
}
.db-question {
    display: flex;
    gap: 50px;
    margin-bottom: 20px;
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
.row {
    display: flex;
    gap: 10px;
    margin-bottom: 10px;
}
.col {
    flex: 1;
    margin-right: 10px;
}
</style>