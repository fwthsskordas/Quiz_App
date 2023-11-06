<!-- eslint-disable vue/multi-word-component-names -->

<script setup>
import { defineProps } from 'vue'; 

const {quiz} = defineProps(['quiz'])
</script>


<template>
    <div class="card">
    <img :src="quiz.img" alt="image">
    <div class="class-text">
        <h2> {{ quiz.name }} </h2>
        <p>{{ quiz.questions.length }} Questions</p>
    </div>
    </div>
</template>





<style scoped>
.card{
  width: 310px;
  overflow: hidden;
  border-radius: 2%;
  box-shadow: 1px 1px 10px rgba(134, 121, 121, 0.7);
  margin-right: 20px;
  cursor: pointer;
  margin-bottom: 35px;
}

.card img{
  width: 100%;
  height: 190px;
  margin: 0;
}

.card .card-text{
  padding: 0 5px;
}

.card .card-text h2{
  font-weight: bold;
  background-color: beige;
}

.class-text{
  background-color: rgb(173, 154, 154);
}

.class-text h2, p{
  font-family: 'Courier New', Courier, monospace;
  color: brown;
  margin-left: 10px;
}

</style>