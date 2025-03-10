<template>
  <div class="barraTop">
    <nav class="menuNav">
      <router-link to="/professores">Professores</router-link>
      <router-link to="/alunos">Alunos</router-link>
      <router-link to="/sobre">Sobre</router-link>
    </nav>
  </div>
</template>

<script>
  export default {
    
  }
</script>

<style scoped>
.barraTop{
  background-color: rgb(35, 85, 141);
}

.menuNav{
}

nav {
  padding: 20px 20px 20px 0px;
}

nav a {
  padding: 10px;
  text-decoration: none;
  background-color: white;
  border-radius: 3px;
  color: rgb(0, 110, 255);
  font-weight: bold;
  margin-right: 15px;
}

nav .router-link-active{
  background-color: rgb(152, 198, 214);
  color: white;
}

</style>