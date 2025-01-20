<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <h1>{{texto}}</h1>
  </div>
</template>
<script>
  export default {
    props: {
      texto: String
    }
  }
</script>

<style scoped>
  h1 {
    display: flex;
    justify-content: center;
    padding: 10px;
    background-color: rgb(40, 120, 211);
    color: white;
    border-radius: 5px;
  }
</style>