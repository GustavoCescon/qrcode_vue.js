<template>
<div class="container">
  <div class="card">
      <div class="qrcode">
        <GeradorQr :msg='nome' v-show="status"/>
      </div>
      <div class="form">
          <input type="text" id="inputForm" v-model="nome">
      </div>
      <div class="tituloCard">
        <h1><strong>Gere seu <a href="">Qrcode</a></strong></h1>
        <h2>Ao digitar o qr code é gerado automaticamente</h2>
      </div>
  </div>
</div>
  
</template>
<script>
  import GeradorQr from './GeradorQr.vue'
  export default {
    name: "Form",
    components:{
      GeradorQr
    },
    data(){
      return{
        nome: '',
        status: true
      }
    },
    methods:{
      gerarQrcode(){
          if(this.nome != ''){
              this.status = true
          }
      }
    }
  }
</script>

<style scoped>
  .container{
    width: 100vw;
    height: 100vh;
    background: #6C7A89;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .card{
    display: flex;
    flex-direction: column;
    background-color: white;
    width: 30em;
    color: black;
    border-radius: .3em;
    padding: 2em;
  }
  .qrcode{
    flex: 1;
  }
  .tituloCard{
    flex: 1;
    text-align: center;
  }
  .tituloCard h1{
    font-family: Helvetica;
    -webkit-font-smoothing: antialiased;
    color: #2c3e50;
    text-align: center;
    font-weight: 600;
    line-height: 1.25;
    margin-top: 1em;
  }
  .tituloCard h2{
    font-family: Helvetica;
    -webkit-font-smoothing: antialiased;
    text-align: center;
    max-width: 35rem;
    font-size: 1em;
    line-height: 1.3;
    color: #6a8bad;
    margin-top: 1em;
  }
  .form{
      flex: 1;
      background-color: white;
      display: flex;
      flex-direction: column;
  }
  #inputForm{
    padding: .6em;
    font-size: 1em;
  }
</style>