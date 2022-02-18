<template>
  <div class="hello">
   <ul v-for="(tarea, index) in tareas" :key="tarea">
      <li><span>{{ index+1 }} - {{ tarea.nombre }}</span>  <button @click="deleteItem(index)">Eliminar x</button></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    tareas: Array
  },
  methods:{
    deleteItem(index){
      this.$emit("deleteItem", index)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  ul{
    display: flex;
    justify-content: center;
  }
  span{
    font-size: 18px;
    font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
    margin-left: 1rem;
  }
  button{
    width: 90px;
    height: 2rem;
    background: rgb(243, 69, 69);
    color: #fff;
    border-radius: 0.3rem;
    margin-left: 1rem;
    border: none;
    font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
    text-transform: uppercase;
  }
</style>
