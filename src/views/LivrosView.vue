<script>
import LivrosApi from "@/api/livros.js";
const livrosApi = new LivrosApi();
export default {
  data() {
    return {
      livro: {},
      livros: [],
    };
  },
  async created() {
    this.livros = await livrosApi.buscarTodosOsLivros();
  },
  methods: {
    async salvar() {
      if (this.livros.id) {
        await livrosApi.atualizarLivro(this.livro);
      } else {
        await livrosApi.adicionarLivro(this.livro);
      }
      this.livros = await livrosApi.buscarTodosOsLivros();
      this.livro = {};
    },
    async excluir(livro) {
      await livrosApi.excluirLivro(livro.id);
      this.livros = await livrosApi.buscarTodosOsLivros();
    },
    editar(livro) {
      Object.assign(this.livro, livro);
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Livros ( Gerenciamento )</h2>
    </div>
    <div class="form-input">
      <input
        type="text"
        v-model="livro.nome"
        @keyup.enter="salvar"
        placeholder="Título do Livro"
      />
      <input
        type="text"
        v-model="livro.isbn"
        @keyup.enter="salvar"
        placeholder="Código ISBN do Livro"
      />
      <input
        type="number"
        v-model="livro.qntd"
        @keyup.enter="salvar"
        placeholder="Quantidade de Livros"
      />
      <input
        type="text"
        v-model="livro.preco"
        @keyup.enter="salvar"
        placeholder="Preço do Livro"
      />
      <button @click="salvar">Add</button>
    </div>
    <div class="list-livros">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Título</th>
            <th>ISBN</th>
            <th>Quantidade</th>
            <th>Preço</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="livro in livros" :key="livro.id">
            <td>{{ livro.id }}</td>
            <td>{{ livro.nome }}</td>
            <td>{{ livro.isbn }}</td>
            <td>{{ livro.qntd }}</td>
            <th>R${{ livro.preco }}</th>
            <td>
              <button class="delete" @click="editar(livro)">Editar</button>
              <button class="delete" @click="excluir(livro)">Excluir</button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap");

.delete {
  background-color: #14213d;
  color: white;
  border: #fca311;
  border-radius: 20px;
  width: 50%;
  height: 30px;
}
.title {
  margin-top: 2rem;
  display: flex;
  justify-content: center;
}
.form-input {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.form-input input {
  width: 20%;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 0 10px;
}

.form-input button {
  margin-left: 1%;
  width: 10%;
  height: 40px;
  border: 1px solid #14213d;
  border-radius: 10px;
  background-color: #14213d;
  color: white;
  font-weight: bold;
  cursor: pointer;
}

.list-livros {
  display: flex;
  justify-content: center;
}

table {
  width: 100%;
  margin: 2% auto;
  border-collapse: collapse;
}

table tr th {
  border: 1px solid #ccc;
  padding: 20px;
  font-weight: bold;
}

table tr td {
  border: 1px solid #ccc;
  padding: 10px;
}

table tr:nth-child(odd) {
  background-color: #ccc;
}
</style>
