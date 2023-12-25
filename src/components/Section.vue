<script setup>
import Question from './Question.vue'

const props = defineProps(['section'])
const emits = defineEmits(['update'])

const updateQuestion = (question, index) => {
    let newQuestions = props.section.questions
    newQuestions[index] = question
    console.log(newQuestions)
    emits('update', Object.assign({}, props.section, {questions: newQuestions}))
}

</script>

<template>
    <h2> {{ props.section.overview }} </h2>
    <Question 
      v-for="(question, index) in props.section.questions"
      :key="index"
      :question="question"
      @update="(question) => updateQuestion(question, index)"
    />
</template>