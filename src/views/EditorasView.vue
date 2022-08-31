<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      Editoras: [
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Hecatonquiro espartano livros",
          site: "Hecatonquiro.holtillock.com.br",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Caves from uranus",
          site: "CravesFromUranos.bing.com.br",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "ornotorinco do bare",
          site: "OrnotorincodoBare.holtillock.com.br",
        },
        {
          id: "02ad4d16-be6b-452a-b0de-24e7cf50266c",
          Nome: "Caves from uranus",
          site: "CravesFromUranos.bing.com.br",
        },
      ],
      novo_nome: "",
      novo_site: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.Editoras.push({
        id: novo_id,
        Nome: this.novo_nome,
        site: this.novo_site,
      });
    },
  },
};
</script>
<template>
  <article id="editora">
    <div class="title">
      <h2>Gerenciador de Editoras</h2>
    </div>
    <div class="editora-input">
      <input type="text" v-model="novo_nome" />
      <input type="text" v-model="novo_site" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="editora-form">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Site</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="Editora in Editoras" :key="Editora.id">
            <td>{{ Editora.id }}</td>
            <td>{{ Editora.Nome }}</td>
            <td>{{ Editora.site }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </article>
</template>

<style>
#editora {
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

.editora-input {
  margin-top: 10px;
  display: flex;
  justify-content: center;
}

.editora-input input {
  width: 60%;
  height: 40px;
  border: 1px solid #ccc;
  border-radius: 10px;
  padding: 0 10px;
}

.editora-input button {
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

.editora-form {
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
