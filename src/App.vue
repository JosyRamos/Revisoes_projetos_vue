<template>
<div class ="corpo">
  <h1 class = "centralizado">{{titulo}}</h1> {{/*ou pode ser usado o v-text="titulo" porem o a interpolação fica de melhor entendimento.*/}}
<table class = "tabela">
  <ul class = "lista-fotos">
  <li v-for="foto of fotos">
    <img v-bind=" foto.url " v-bind:alt="foto.titulos">{{/*ou pode ser usado :src que funciona do mesmo jeito*/}}
  </li>
  </ul>

</table>

  </div>
</template>

<script>
export default {
  data(){
    return{
      titulo:'Cachorros de Várias cores',
      fotos:[ ]
    }
  },
  created(){
   let promise = this.$http.get('http://localhost:8080/v2/projetodaJosi');
   promise.then(res  => {
     res.json().then(fotos => this.fotos = fotos);{{/*pode ser usada de varias formas! porem é o mesmo resultado*/}}
   });

  }
  

}
</script>

<style>
.corpo{
  font-family:'Times New Roman', Times, serif; 
  color: hotpink;
  width:96%;
  margin-top:0 auto;
}
.centralizado{
color: darkslateblue;
text-align: center;
}

</style>
