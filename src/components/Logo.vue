<template>
  <div>
      <img src="../assets/logo.png" alt="">
      <p>{{ bienvenue||"Bienvenue !" }}</p>
      <button @click="sentbounce"> Bounces with parent : {{bounces}}</button>
  </div>
</template>

<script>

export default {
    name: "Logo",
    props: [
        "bienvenue",
        'bounces'],
    
    methods:{
        sentbounce(){
            this.$emit('sendBounce')
        }

    }
}
</script>

<style scoped>
    img{
        height:300px
    }

</style>