<template>
  <div class="layout">
    <label for="mailinput">Correos electrónicos:</label>
    <textarea
      rows="8"
      class="area"
      placeholder="Ingresa los correos separados por un espacio"
      v-model="textAreaValue"
    ></textarea>
    <p>
      {{ properMails.length }} correos
    </p>
  </div>
</template>

<script>
import { mailRegex } from "../constants";

export default {
  name: 'MailInput',
  data() {
    return {
      textAreaValue: "",
    }
  },
  methods: {
    handleChange(val) {
      return this.$emit("changeTextarea", val)
    },
  },
  computed: {
    properMails() {
      const inputed = this.textAreaValue.split(" ");
      return inputed.filter(m => mailRegex.test(m));
    },
  },
  watch: {
    textAreaValue: function() {
      this.handleChange(this.properMails);
    }
  }
}
</script>

<style scoped>
.layout {
  width: 100%;
}

.layout > label{
  margin-bottom: 0.8rem;
  display: block;
  text-align: left;
  color: #666666;
}
.layout > .area {
  box-sizing: border-box;
  padding: 1rem;
  border-color: #888888;
  border-radius: 0.5rem;
  width: 100%;
  resize: none;
}
.layout > .area:focus {
  outline: none;
}
</style>
