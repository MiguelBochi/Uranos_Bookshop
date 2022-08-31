<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      Generos: [
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Shoujo",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Fantasia",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Acao",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Terror",
        },
      ],
      novo_nome: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.Generos.push({
        id: novo_id,
        Nome: this.novo_nome,
      });
    },
  },
};
</script>
<template>
  <article id="genero">
    <div class="title">
      <h2>Gerenciador de Generos</h2>
    </div>
    <div class="genero-input">
      <input type="text" v-model="novo_nome" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="genero-form">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="Genero in Generos" :key="Genero.id">
            <td>{{ Genero.id }}</td>
            <td>{{ Genero.Nome }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </article>
</template>

<style>
#genero {
  width: 900px;
  max-height: 100%;
  min-height: 600px;
  background-color: #d9ccc1;
  border-radius: 15px;
  padding: 20px;
  margin-bottom: 30px;
}
.title {
  display: flex;
  justify-content: center;
}

.genero-input {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.genero-input input {
  width: 60%;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 0 10px;
}

.genero-input button {
  margin-left: 1%;
  width: 20%;
  height: 40px;
  border: 1px solid #6d8c89;
  border-radius: 10px;
  background-color: #6d8c89;
  color: white;
  font-weight: bold;
  cursor: pointer;
}

.genero-form {
  display: flax;
  justify-content: center;
}

table {
  width: auto;
  margin: 2% auto;
  border-collapse: collapse;
}

table tr th {
  border: 1px solid rgb(0, 0, 0);
  padding: 10px;
  font-weight: bold;
}

table tr td {
  border: 1px solid rgb(0, 0, 0);
  padding: 10px;
}

table tr:nth-child(odd) {
  background-color: #ccc;
  color: black;
}
</style>
