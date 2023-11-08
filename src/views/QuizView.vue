<script setup>
import Question from "../components/Question.vue"
import QuizHeader from "../components/QuizHeader.vue"
import { useRoute } from "vue-router"
import { ref,  computed } from "vue"
import quizes from "../data/quizes.json"
import Result from "../components/Result.vue"

const route = useRoute()
const quizId = parseInt(route.params.id)
const quiz = quizes.find(q => q.id === quizId)
const currentQuestion = ref(0);
const numberOfCorrectAnswers = ref(0)


// watch(() => cuurentQuestion.value, () => {
//     questionStatus.value = `${cuurentQuestion.value}/${quiz.questions.length}`
// })

const questionStatus = computed(() => `${currentQuestion.value}/${quiz.questions.length}`)
const barPercentage = computed(() => `${currentQuestion.value}/${quiz.questions.length * 100}%`)



const onOptionSelected = (isCorrect) => {
    if (isCorrect) {
        numberOfCorrectAnswers.value++;
    }

    currentQuestion.value++;
 }
</script>

<template>
    <div>
        <QuizHeader :questionStatus="questionStatus"
        :barPercentage="barPercentage"
        />
        <div>
            <Question :question="quiz.questions[cuurentQuestion]" @selectOption="onOptionSelected"/>
            <Result /> 
        </div>
    </div>
</template>
