<template>
<section class="src-components-codificacion">
    Color: <input type="text" v-model="color">
    Fondo: <input type="text" v-model="fondo">
    Size: <input type="text" v-model="size">
    <hr>
    Texto: <input type="text" :style="{color: color, background:fondo, fontSize: size}" v-model="ingreso">
    <p>{{contar}}</p>  

    <div class="table-responsive">
        <table class="table table-light">
          <tr>
            <th>Numero de pregunta</th>
            <th>Respuesta</th>
          </tr>
          <tr v-for="(pregunta, index) in preguntas" :key="index">
            <td>{{pregunta.numero}}</td>
            <td>{{pregunta.respuestas}}</td>
          </tr>
        </table>
      </div>      

</section>
</template>

<script>
export default  {
    name: 'src-components-codificacion',
    props: [],
    data () {
      return {
        ingreso: "",
        color: "",
        fondo: "",
        size: "",
        preguntas : [ 
            { numero: 1, respuestas: ['B'] },
            { numero: 2, respuestas: ['C'] },
            { numero: 3, respuestas: ['B'] },
            { numero: 4, respuestas: ['D'] },
            { numero: 5, respuestas: ['B'] },
          ]
      }
        
      },

    mounted () {
    },
    methods: {
    },
    computed: {
        contar:function(){            
        return "Cantidad: " + this.ingreso.split(" ").length;
      },
  
    },
}
</script>

<style scoped lang="css">
</style>