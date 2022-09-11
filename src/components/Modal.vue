<template>
  <div>
    <h1>{{ answerVal }}</h1>
    <div class="btn-container">
      <Yes :answer="answer" @set-answer="setAnswer" />
      <Sometimes :answer="answer" @set-answer="setAnswer" />
      <No :answer="answer" @set-answer="setAnswer" />
    </div>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

import Yes from './Buttons/Yes.vue'
import Sometimes from './Buttons/Sometimes.vue'
import No from './Buttons/No.vue'

const answer = ref(null)

const answerVal = computed(() => {
  
  return answer.value
})

const setAnswer = (newAnswer) => {
  answer.value = newAnswer
}
</script>

<style scoped>
.btn-container {
  display: flex;
  flex-flow: row nowrap;
}
</style>
