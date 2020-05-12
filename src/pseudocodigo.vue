<template>
  <div class="container">
    <br><br>
    <div class="row justify-content-md-center">
      <table class="table">
        <thead class="thead-dark">
          <tr>
            <th scope="col">Serie de Fabonacci</th>
          </tr>
        </thead>
        <tr>
          <td>
            Incio
          </td>
        </tr>
        <tr>
          <td>
            Escribir “Ingresa un numero"
          </td>
        </tr>
        <tr>
          <td>
            a = 0
            b = 1
          </td>
        </tr>
        <tr>
          <td>
            si (x  >= 1 &&  x <= 12) entonces <br>
              ciclo ( i = 2  i < x i++)<br>
                c = a + b<br>
                a = b<br>
                b = c<br>
              Fin del cliclo<br>
            Fin<br>
            Sino ( Mensaje “El numero Ingresado no es valido”)<br>
            Fin<br>
          </td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
 name: 'pseudocodigo',
}
</script>

<style>

</style>

