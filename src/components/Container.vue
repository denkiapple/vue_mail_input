<template>
  <div class="container">
    <h1>{{ msg }}</h1>
    <div>
      <MailInput v-on:changeTextarea="updateMails($event)" />
      <MailList v-if="mails.length > 0" :list="mails" />
    </div>
  </div>
</template>

<script>
import MailInput from './MailInput.vue'
import MailList from './MailList.vue'

export default {
  name: 'Container',
  data() {
    return {
      mails: [],
    }
  },
  methods: {
    updateMails(e) {
      this.mails = e;
    }
  },
  components: {
    MailInput,
    MailList,
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
  transition: all 600ms;
}

.container:hover {
  box-shadow: 0.25rem 0.25rem 0.5rem #DDDDDD;
}

.container > div {
  display: flex;
  flex-direction: row;

}

h1 {
  margin-top: 0;
}
</style>
