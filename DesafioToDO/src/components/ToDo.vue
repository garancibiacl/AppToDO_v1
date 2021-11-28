<template>
  <div class="container">
    <div class="row">
      <div class="col-12 pt-5 pt-4">
        <h1>Aplicación de Administración de Tareas</h1>
      </div>

      <div class="col-12 p-5">
       
              <div class="shadow p-5 mb-5 mb-2 bg-light rounded ">
                 <div class="row">
                <div class="col-6 text-center ">
                <h3 class="text-danger  title-num">10</h3>
                <p>Tareas Completadas</p>
                </div>
                 <div class="col-6 text-center">
                <h3 class="text-danger  title-num">4.6</h3>
                <p>Tiempo Transcurrido(h)</p>
                </div>
                </div>

              </div>
        <h2 class="fw-bold">Hoy</h2>
<i class="bi bi-plus"></i>
        <div class="input-group mb-3">
          <input
            type="text"
          name="task"
            v-model="task"
            @keydown.enter="insert"
            class="form-control"
            placeholder="Añadir nueva tarea en Tareas, Presione la tecla enter o presionar Agregar Tarea"
            aria-label="Recipient's username"
            aria-describedby="button-addon2"
          />
          <button
            @click="insert"
            class="btn btn-outline-secondary"
            type="button"
            id="button-addon2"
          >
            Agregar Tarea
          </button>
        </div>
      </div>
      <div class="col-12 p-5">
        <h2 class="fw-bold">Tareas</h2>
          <ul class="tasks">
            <li v-for="(item, index) in list" :key="index">
              {{ index + 1 }}: {{ item }}
            </li>
          </ul>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      task: "",
      list: [],
    };
  },
  methods: {
    insert() {
      this.list.push(this.task);
      this.task = "";
    },
  },
};
</script>

<style scoped>
body{
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

.container {
  width: 100%;
  margin: 1em auto;
  font-family: sans-serif;
  background-color: #f2f0f0;
}
label {
  font-weight: 800;
  margin-right: 0.3em;
}
button {
  margin-left: 0.3em;
}
h1 {
  color: #151515;
  text-align: center;
  font-size: 2rem;
}
h2 {
  color: #525252;
  text-align: left;
  font-size: 1.5rem;
}
ul {
width: 100%;
  text-align: left;
  background-color: white;
  list-style: none;
  padding: 1rem;
  border-radius: 7px;
  height: 230px;
}
li {
  font-weight: 700;
}
.title-num{
  font-size: 3rem;
}
p{
  color: #a1a2a3;
}

</style>
