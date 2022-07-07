<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      Autores: [
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Machado de Assis",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Monteiro Lobato",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Thiago Nigro",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Rupi Kaur",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Anna Todd",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Paulo Coelho",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Ziraldo Alves Pinto",
        },
      ],
      novo_nome: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.Autores.push({
        id: novo_id,
        Nome: this.novo_nome,
      });
    },
  },
};
</script>
<template>
  <article id="autor">
    <div class="title">
      <h2>Autores</h2>
    </div>
    <div class="autor-input">
      <input type="text" v-model="novo_nome" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="autor-form">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Autor</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="Autor in Autores" :key="Autor.id">
            <td>{{ Autor.id }}</td>
            <td>{{ Autor.Nome }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </article>
</template>

<style>
#autor {
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

.autor-input {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.autor-input input {
  width: 60%;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 0 10px;
}

.autor-input button {
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

.autor-form {
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
