<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
import { defineProps, defineEmits } from 'vue';

const { question } = defineProps(['question'])
const emit = defineEmits(['selectOption']);

const emitSelectedOption = (isCorrect) => {
    emit("selectOption", isCorrect)
}
</script>


<template>
    <div class="question-container">
        <h1 class="question">
          {{question.text}}
        </h1>
    </div>
    <div class="options-container">
        <div v-for="option in question.options" :key="option.id" class="option" @click="emitSelectedOption(option.isCorrect)">
            <p class="option-label">{{option.label}}</p>
                <div class="option-value">
                    <p>{{option.text}}</p>
                </div>
        </div>
    </div>
</template>


<style scoped>
    .question-container {
        margin-top: 20px;
    }

    .question{
        font-size: 40px;
        margin-bottom: 20px;
    }

    .option {
        display: flex;
        margin-bottom: 20px;
        cursor: pointer;    
    }

    .option-label {
        display: flex;
        font-size: 30px;
        cursor: pointer;    
        background-color: blueviolet;
        width: 50px;
        height: 50px;
        align-items: center;
        justify-content: center;
        border-radius: 5px;
        color: azure;
    }

    .option-value {
        margin-top: 30px;
        background-color: aliceblue;
        width:  100%;
        height: 50px;
        font-size: 30px;
        padding: 0 20px;
    }

    .option-value p{
        margin-top: 8px;
    }
</style>