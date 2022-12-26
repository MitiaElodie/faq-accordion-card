<template>
  <div class="dropdown__container">
    <div class="dropdown__question-container">
      <span class="dropdown__question">{{ question }}</span>
    </div>
    <div class="dropwdown__answer-container">
      {{ answer }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    question: {
      type: String,
      default: '',
    },
    answer: {
      type: String,
      default: '',
    },
  }
}
</script>

<style>

</style>
