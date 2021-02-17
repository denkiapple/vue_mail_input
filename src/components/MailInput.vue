<template>
  <div class="layout">
    <label for="mailinput">Correos electrónicos:</label>
    <textarea
      id="mailinput"
      name="mailinput"
      rows="8"
      class="area"
    ></textarea>
  </div>
</template>

<script>
export default {
  name: 'MailInput',
  props: {
  }
}
</script>

<style scoped>
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
