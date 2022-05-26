<template>
  <div>
    <Form/>
  </div>
</template>

<script>
  import Form from './components/Form.vue'

export default {
  name: 'App',
  components:{
    Form
  }
  
}
</script>

<style>

  *{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }
  body{
    background: #26282B;
  }
</style>
