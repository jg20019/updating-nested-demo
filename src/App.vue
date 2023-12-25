<script setup>
import { ref } from 'vue'
import Faq from './components/Faq.vue'

const faq = ref({
  title: 'Test Faq',
  sections: [
    {
      overview: 'Section 1',
      questions: [
        { questionText: 'Question 1', answerText: 'Answer 1' },
        { questionText: 'Question 1', answerText: 'Answer 1' },
        { questionText: 'Question 1', answerText: 'Answer 1' },
      ]
    },
    {
      overview: 'Section 2',
      questions: [
        { questionText: 'Question 1', answerText: 'Answer 1' },
        { questionText: 'Question 1', answerText: 'Answer 1' },
        { questionText: 'Question 1', answerText: 'Answer 1' },
      ]
    },
  ]
})

const updateFaq = (newFaq) => { 
  faq.value = newFaq
}
</script>

<template>
  <main>
    <Faq :faq="faq" @update="updateFaq" />
    <pre> {{ faq }} </pre>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

main {
  display: flex;
}
</style>
