<script setup>
import LicenseAgreement from './components/LicenseAgreement.vue';
</script>

<template>
  <div class="card">
    <h1>FDSA Installer</h1>
    <LicenseAgreement />
    <p>
      By clicking "Accept", you agree to the terms of the license agreement.
      If you do not agree, you may not use the software.
    </p>
    <p class="buttons">
      <button @click="$emit('accept')">Accept</button>
      <button @click="$emit('decline')">Decline</button>
    </p>
  </div>
</template>

<style scoped>
.card {
  width: 80%;
  margin: 0 auto;
  padding: 20px;
  border-radius: 8px;
  background-color: #bfdbe9;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.236);
  height: 800px;
}
.card h1 {
  font-size: 24px;
  margin-bottom: 20px;
}
.buttons {
  display: flex;
  justify-content: center;
  gap: 20px;
}
.buttons button {
  padding: 10px 20px;
  border: none;
  border-radius: 4px;
  color: white;
  cursor: pointer;
}
.buttons button:first-child {
  background-color: #007bff;
}
.buttons button:last-child {
  background-color: #dc3545;
}

.buttons button:first-child:hover {
  background-color: #0056b3;
}
.buttons button:last-child:hover {
  background-color: #c82333;
}

</style>
