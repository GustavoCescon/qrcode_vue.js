<template>
<div class="qrCode">
  <qrcode-vue :value="msg" :size="size" level="H"/>
</div>
  
</template>
<script>
  import QrcodeVue from 'qrcode.vue'

  export default {
    name: "GeradorQrcode",
    data() {
      return {
        size: 150
      }
    },
    components: {
      QrcodeVue,
    },
    props:{
      msg: String,
      status: Boolean
    }
  }
</script>

<style scoped>
  .qrCode{
    justify-content: center;
    align-items: center;
    text-align: center;
  }
</style>