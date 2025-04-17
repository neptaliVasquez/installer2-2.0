<script setup>
import { ref } from 'vue';
// import LicenseAgreement from './components/LicenseAgreement.vue';
// import ExternalDatabase from './components/ExternalDatabase.vue';
import SubdomainChoice from './components/SubdomainChoice.vue';

const page=ref(1); 

</script>

<template>
  <div class="card">
    <h1>FDSA Installer</h1>
    <!-- <LicenseAgreement /> -->
    <!-- <ExternalDatabase/> -->
    <SubdomainChoice />
  </div>
</template>

<style scoped>
.card {
  margin: 0 auto;
  padding: 20px;
  border-radius: 8px;
  background-color: #bfdbe9;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.236);
  height: 850px;
}
.card h1 {
  font-size: 24px;
  margin-bottom: 20px;
  color: #333;
  text-align: center;
}

</style>
