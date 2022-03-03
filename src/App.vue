<template>
<div>
  <h1>{{titulo}}</h1> {{/*ou pode ser usado o v-text="titulo" porem o a interpolação fica de melhor entendimento.*/}}

<ul>
  <li v-for="foto of fotos">
    <img :src=" foto.url " :alt="foto.titulos">{{/*ou pode ser usado :src que funciona do mesmo jeito*/}}
  </li>
  </ul>
  </div>
</template>

<script>
export default {
  data(){
    return{
      titulo:'Cachorros de Várias cores',
      fotos:[{
         url:"https://img.freepik.com/fotos-gratis/cachorro-preto-grande_168440-185.jpg",
        titulos:"Cachorro preto grande"
      },
      {
         url:"https://static1.patasdacasa.com.br/articles/0/17/60/@/8421-pastor-branco-suico-se-apaixone-tambem-articles_media_mobile-2.jpg",
        titulos:"Pastor Branco Suiço"
      }
     ]
    }
  }
 
}
</script>

<style>

</style>
