<template>
  <div class="layout">
    <div>
      <p v-for="mail in list" :key="mail" class="mailChip">
        {{ mail }}
      </p>
    </div>
    <button class="button">
      Mandar correo{{ list.length > 1 ? "s" : "" }}
    </button>
  </div>
</template>

<script>
export default {
  name: 'MailList',
  props: {
    list: [],
  },
}
</script>

<style scoped>
.layout {
  width: 100%;
  margin-left: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.mailChip {
  box-sizing: border-box;
  width: 100%;
  margin: 0.5rem 0;
  border: 1px solid #59c95c;
  background-color: #e6ffe6;
  border-radius: 0.5rem;
  text-align: left;
  padding: 0.5rem 0.8rem;
  font-size: 1rem;
}

.button {
  border: none;
  padding: 0.8rem;
  border-radius: 0.25rem;
  background-color: #fd8797;
  color: white;
  font-weight: bold;
  transition: all 600ms;
  cursor: pointer;
}

.button:hover {
  box-shadow: 0.15rem 0.25rem 0.5rem #CCCCCC;
}

.button:focus {
  background-color: #db7280;
  outline: none;
}
</style>
