<template>
<div class="container">
  <div class="row justify-content-md-center">
    <center>
      <table class="table table-striped" id="contenido">
          <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">1</th>
            <th scope="col">2</th>
            <th scope="col">3</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(valor, index) in listado"
          :key="valor.index"
          >
            <td style="color:blue">
              {{index}}
            </td>
            <td>
              {{listado[index -2]}}
            </td>
            <td>
              {{listado[index -1]}}
            </td>
            <td style="color:red">
              {{valor }}
            </td>
          </tr>
        </tbody>
      </table>
    </center>
  </div>
</div>
</template>

<script>
export default {
 name: 'tabla',
 data(){
   return {

   }
 },
 props:{
    listado: {
      required: true
    }
  }
}

</script>

<style>

#contenido {
  font-weight: normal;
  align-content: center;
}

</style>
