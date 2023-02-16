<script setup>
import Balance from './components/Balance.vue';
import Spending from './components/Spending.vue'
import data from '../src/data/data.json'
import { ref } from 'vue';

const spending = ref(data);


</script>

<template>
  <div class="container">
    <header>
      <Balance />
    </header>
    <main>
      <Spending :spending="spending" />
    </main>
  </div>

</template>

<style scoped>
.container {
  height: 100vh;
  width: 93%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  justify-content: center;

}

.container header {
  margin-bottom: 18px;
}
</style>
