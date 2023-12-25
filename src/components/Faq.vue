<script setup>
import Section from './Section.vue'

const props = defineProps(['faq'])
const emit = defineEmits(['update'])

const updateSection = (section, index) => {
    let newSections = props.faq.sections
    newSections[index] = section
    emit('update', Object.assign({}, props.faq, { sections: newSections}))
}
</script>

<template>
    <div class="faq">
    <h1> {{props.faq.title}} </h1> 
    <Section 
     v-for="(section, index) in props.faq.sections" 
     :key="index"
     :section="section"
     @update="(section) => updateSection(section, index)"
     />
    </div>
</template>

<style scoped>
.faq {
    display: flex;
    flex-direction: column;
}
</style>