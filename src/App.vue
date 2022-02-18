<template>
  <div>
    <h1>Mi lista de tareas</h1>
    <form v-on:submit.prevent="agregarTarea">
      <label>Nueva Tarea</label>
      <input type="text" v-model="nombre" />
      <button class="btn" type="submit">Agregar Tarea</button>
    </form>

    <h2>Esta es mi lista de tareas .</h2>

    <HelloWorld :tareas="this.tareas" @deleteItem="deleteItem"/>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";

export default {
  name: "App",
  data() {
    return {
      nombre: "",
      tareas: [],
    };
  },
  methods: {
    agregarTarea: function () {
      this.tareas.push({
        nombre: this.nombre,
      })
      this.nombre = ""
    },
    deleteItem(index){
      this.tareas.splice(index, 1)
    }
  },
  components: {
    HelloWorld,
  },
};
</script>

<style>
label{
  font-size: 18px;
  text-transform: uppercase;
  margin-right: 1rem;
}
input{
  width: 200px;
  height: 25px;
  margin-right: 1rem;
}
.btn{
  height: 2rem;

}
body{
  display: flex;
  justify-content: center;
}
</style>
