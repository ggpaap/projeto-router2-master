<script>
import { v4 as uuidv4 } from "uuid";
export default {
  data() {
    return {
      times: [
        { id: "4dfadc62-3011-48a9-a384-53cbc062b0b2", nome: "Time 1" },
        { id: "6fe0c8e2-619b-4c46-b92b-e1ca7a3b970c", nome: "TIme 2" },
        { id: "9e3a44e1-bceb-4786-a1fd-38c5a76a7745", nome: "Time 3" },
      ],
      novo_time: "",
    };
  },
  methods: {
    salvar() {
      const novo_id = uuidv4();
      this.times.push({
        id: novo_id,
        nome: this.novo_time,
      });
    },
  },
};
</script>

<template>
  <div class="container">
    <div class="title">
      <h2>Gerenciamento de Times</h2>
    </div>
    <div class="form-input">
      <input type="text" v-model="novo_time" />
      <button @click="salvar">Salvar</button>
    </div>
    <div class="list-times">
      <table>
        <thead>
          <tr>
            <th>ID</th>
            <th>Nome</th>
            <th>Ações</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="time in times" :key="time.id">
            <td>{{ time.id }}</td>
            <td>{{ time.nome }}</td>
            <td>???</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
  <RouterView />
</template>

<style>
.title {
  text-align: center;
  margin: 2rem 0;
}

.form-input {
  display: flex;
  justify-content: center;
  margin: 2rem 0;
}

.form-input input {
  width: 50%;
  padding: 0.5rem;
  border: 5px solid #98b7e1;
  border-radius: 10px;
}

.form-input button {
  padding: 0.5rem;
  border: 5px solid #98b7e1;
  border-radius: 10px;
  color: #454663;
  font-weight: bold;
  margin-left: 1%;
}

.list-times {
  display: flex;
  justify-content: center;
}

table {
  width: 80%;
  border-collapse: collapse;
  margin: 0 auto;
  border: 1px solid #9bfae2;
  font-size: 1.1rem;
  text-align: center;
}

table thead {
  background-color: #98b7e1;
  color: #454663;
}

table thead th {
  font-weight: bolder;
}

table tbody tr:nth-child(odd) {
  background-color: #4f374d;
}
</style>
