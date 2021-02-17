<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <MailInput />
  </div>
</template>

<script>
import MailInput from './MailInput.vue'

export default {
  name: 'Container',
  components: {
    MailInput
  },
  props: {
    msg: String
  }
}
</script>

<style scoped>
.container {
  background-color: #FFFFFF;
  padding: 1.5rem;
  border-radius: 0.5rem;
  transition: all 600ms;
}

.container:hover {
  box-shadow: 0.25rem 0.25rem 0.5rem #DDDDDD;
}

h1 {
  margin-top: 0;
}
</style>
