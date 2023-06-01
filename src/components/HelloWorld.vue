<script setup lang="ts">
defineProps<{
  msg: string
}>()
</script>

<template>
  <div class="greetings">
    <h1 class="green">{{ msg }}</h1>
  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

.greetings h1 {
  margin: 0 auto;
  font-family: 'Fredoka One', sans-serif;
  font-size: 2.75em;
}

.greetings {
  height: 7em;
  background-color: #bbe998bb;
  display: flex;
  align-items: center;
}
</style>
