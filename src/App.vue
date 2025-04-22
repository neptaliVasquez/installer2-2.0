<script setup>
import { ref } from 'vue';
import LicenseAgreement from './components/LicenseAgreement.vue';
import ExternalDatabase from './components/ExternalDatabase.vue';
import SubdomainChoice from './components/SubdomainChoice.vue';

const page=ref(1); 

const nextPage = () => {
  if (page.value === 1) {
    page.value = 2;
  } else if (page.value === 2) {
    page.value = 3;
  } else if (page.value === 3) {
    page.value = 4;
  }
};



</script>

<template>
  <div class="card">
    <h1>FDSA Installer</h1>
    <LicenseAgreement v-if="page===1" @accept="nextPage"/> 
    <ExternalDatabase v-if="page===2" @nextPage="nextPage"/> 
    <SubdomainChoice v-if="page===3"/>
  </div>
</template>

<style scoped>
.card {
  margin: 0 auto;
  padding: 20px;
  border-radius: 8px;
  background-color: #cde4e4;
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
