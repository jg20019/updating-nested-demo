<script setup>
const props = defineProps(['question'])
const emit = defineEmits(['update'])

const updateQuestionText = (questionText) => {
    emit('update', { questionText, answerText: props.question.answerText })
}

const updateAnswer = (answerText) => {
    emit('update', { questionText: props.question.questionText, answerText })
}
</script>

<template>
    <div>
        <input type="text" :value="props.question.questionText" @input="(e) => updateQuestionText(e.target.value)" />
        <br>
        <input type="text" :value="props.question.answerText" @input="(e) => updateAnswer(e.target.value)" />
    </div>
</template>

<style scoped>
div {
    margin-bottom: 10px;
}
</style>