<template>
<div class="container">
  <div class="card">
      <div class="qrcode">
        <GeradorQr :msg='nome' v-show="status"/>
      </div>
      <div class="form">
          <input type="text" id="inputForm" v-model="nome" placeholder="Digite o conteúdo">
      </div>
      <div class="tituloCard">
        <h1><strong>Gere seu <a target="_blank" v-bind:href="url">Qrcode</a></strong></h1>
        <h2>Ao digitar o <a target="_blank" v-bind:href="url">Qrcode</a> é gerado automaticamente</h2>
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
        url: "https://www.npmjs.com/package/qrcode.vue",
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
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .card{
    display: flex;
    flex-direction: column;
    background-color: white;
    width: 25em;
    color: #151626;
    padding: 2em;
    border-top: 8px solid #4169e1;
    border-radius: 3px 3px 3px 3px;
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
    text-align: center;
    font-weight: 600;
    line-height: 1.25;
    margin-top: 1em;
  }
  .tituloCard h1 a, .tituloCard h2 a{
    color: #4169e1;
    text-decoration: none;
  }
  .tituloCard h2{
    font-family: Helvetica;
    -webkit-font-smoothing: antialiased;
    text-align: center;
    max-width: 35rem;
    font-size: 1em;
    line-height: 1.3;
    margin-top: 1em;
    opacity: 0.7;
  }
  .form{
      flex: 1;
      display: flex;
      flex-direction: column;
  }
  #inputForm{
    padding: .6em;
    font-size: 1em;
    border: none;
    border-bottom: 2px solid #151626;
    cursor: pointer;
    margin-top: 2em;
    background-color: transparent;

  }
  #inputForm:focus{
    border-bottom: 2px solid #151626;
    outline: 0;
  }
</style>