<template>
  <div id="app">
    <Alunos/>
  </div>
</template>

<script>
import Alunos from './components/Aluno/Alunos.vue'

export default {
  name: 'app',
  components: {
    Alunos
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@1,900&display=swap');

#app {
}

body,html{
  margin: 0;
  height: 100%;
  padding: 0;
  box-sizing: border-box;
}

body {
  background-color: rgb(185, 216, 250);
  font-family: 'Roboto', sans-serif;
  display: grid;
  justify-items: center;
}

.btn_Danger{
  background-color: rgb(47, 103, 167);
}

.btn {
  padding: 10px 20px;
  cursor: pointer;
  border: 1px solid #000;
  color: #fff;
  font-weight: bold;
  border-radius: 5px;
  border-bottom: 3px solid #000;
}

.btn:hover {
  background-color: rgb(35, 85, 141);
  text-shadow: 1px 1px 1px #000;
  margin-top: 3px;
  border-bottom: 1px solid #000;
}

table {
  margin: 0;
  padding: 0;
  list-style-type: none;
  width: 100%;
}

table tr td{
  padding: 20px;
  font-size:  1em;
  background-color: rgb(152, 198, 214);
  margin-bottom: 2px;
}

table thead th{
  background-color: rgb(40, 120, 211) !important;
  font-size: 1.3em;
  padding: 10px 0px;
  text-align: center !important;
  color: white;
}

.colPequeno {
  width: 5%;
}
</style>