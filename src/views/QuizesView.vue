<script setup>
import q from "../data/quizes.json"
import { ref } from "vue";  
import { watch } from "vue";
import Card from "../components/card.vue"


const quizes = ref(q);
const search = ref(""); 

watch(search, () => {
  quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
})
</script>

<template>
  <div>
    <header>
      <h1>Quizes</h1>
      <input v-model.trim="search" type="text">
    </header>
    <div class="option-container" placeholder="Search Quiz Here!">
        <card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz"/>
    </div>
  </div>
</template>



<style scoped>
 header {
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
 }

 header h1 {
  font-weight: bold;
  margin-right: 30px;
 }

 header input {
  margin-top: 8px;
  border: none;
  background-color: rgba(255, 255, 255, 0.76);
  padding: 10px;
  border-radius: 10px;
 }
.option-container {
  display: flex;
  flex-wrap: wrap;
  margin-top: 40px;
}
</style>