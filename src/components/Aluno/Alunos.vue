<template>
  <div>
    <titulo texto="Lista de Alunos"/>
    <div>
      <input type="text" placeholder="Nome do Aluno" v-model="nome" v-on:keyup.enter="addAluno()">
      <button class="btn btnInput" @click="addAluno()">Adicionar</button>
    </div>

    <table>
      <thead>
        <th>ID</th>
        <th>Nome</th>
        <th>Opções</th>
      </thead>
      <tbody v-if="alunos.length">
        <tr v-for="(aluno, index) in alunos" :key="index">
          <td>{{aluno.id}}</td>
          <td>{{aluno.nome}} {{aluno.sobrenome}}</td>
          <td>
            <button class="btn btn_Danger" @click="remover()">Remover</button>
          </td>
        </tr>
      </tbody>
      
    </table>
    <div class="footer">
      <tfoot v-if="!alunos.length">
        Nenhum Aluno Encontrado
      </tfoot>
    </div>

  </div>
</template>

<script>
import Titulo from '../../components/_share/Titulo'

export default {
  components:{
    Titulo
  },
  name: 'ListaAlunos',
  data(){
    return {
      alunos: []
    }
  },
  created() {
    this.$http
    .get('http://localhost:3000/alunos')
    .then(res => res.json())
    .then(alunos => this.alunos = alunos)
  },
  props: {
  },
  methods: {
    addAluno(){
      let _aluno = {
        id: this.alunos.length + 1,
        nome: this.nome,
        sobrenome: ""
      }
      this.$http
      .post('http://localhost:3000/alunos', _aluno)
      .then(res => res.json())
      .then(() => {
        this.alunos.push(_aluno);
        this.nome = '';
      })
    },
    remover(aluno){
      this.$http
      .delete(`http://localhost:3000/alunos/${aluno.id}`)
      .then(() => {
        let indice = this.alunos.indexOf(aluno);
        this.alunos.splice(indice, 1);
      })
    }
  }
}
</script>
<style scoped>
  input{
    margin-bottom: 10px;
    border-radius: 5px 0px 0px 5px;
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    color: #687f7f;
    display: inline;
  }

  .btnInput {
    width: 150px;
    border: 0;
    padding: 20px;
    font-size: 1.3em;
    background-color: rgb(47, 103, 167);
    border-radius: 0px 5px 5px 0px;
  }

  .btnInput:hover{
    background-color: rgb(35, 85, 141);
    margin: 0;
    border: 0;
  }

  .footer {
    display: flex;
    justify-content: center;
    color: #5f5d5d;
    margin-top: 25px;
    font-size: 1.5em;
  }
</style>