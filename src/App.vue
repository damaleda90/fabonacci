<template>
  <div id="app">
    <div class="row">
      <div class="col-md-12">
        <h2>Serie de Fabonacci</h2>
        <span>Ingresa un Numero:</span>
        <input type="number" placeholder="Numero del 1 al 12" v-model="parametros.numero" id="numero">
        <button id="calcular" class="btn btn-success" @click="calcular">Calcular</button>
        <button id="mostrar" class="btn btn-info" @click="mostrar">Pseudocodigo</button>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12">
        <pseudocodigo
        v-show="mostrarPseudocodigo"
        >
        </pseudocodigo>
      </div>
    </div>
    <div class="row">
      <div class="col-md-12" v-show="parametros.mostrar">

        <tabla v-show="parametros.valido == true"
         :listado = "parametros.content"
        >
        </tabla>

        <div class="alert alert-danger" role="alert" v-show="parametros.valido == false" >
            {{parametros.content}}
        </div>

      </div>
    </div>

  </div>
</template>

<script>
import tabla from './tabla';
import pseudocodigo from './pseudocodigo';
import BootstrapVue from 'bootstrap-vue';
import "bootstrap/dist/css/bootstrap.min.css";
import "bootstrap-vue/dist/bootstrap-vue.css"

export default {
  name: 'app',
  data () {
    return {
      parametros: {
        numero:'',
        mostrar: false,
        content: [],
        valido:'',
      },
      mostrarPseudocodigo: false
    }
  },
  components:{
    tabla,
    pseudocodigo
  },
  methods: {
    calcular() {

      let listado = [0,1];
      let serie = parseInt(this.parametros.numero) + 1

      if (this.parametros.numero >= 1 && this.parametros.numero <= 12)
      {
        for (let valor = 2; valor < serie; valor++) {

        listado[valor] = listado[ valor - 2] + listado[valor - 1];

        }
        this.parametros.valido = true;
        this.parametros.mostrar = true;
        this.parametros.content = listado;

      }else {
        this.parametros.valido = false;
        this.parametros.mostrar = true;
        this.parametros.content = "El numero Ingresado no es Valido";
      }
    },
    mostrar(){
      if(this.mostrarPseudocodigo == false )
        {
          this.mostrarPseudocodigo = true
        }else {
          this.mostrarPseudocodigo = false
        }

    }

    },
  }
</script>

<style>

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h2 {
  font-weight: normal;
  align-content: center;
}

</style>
