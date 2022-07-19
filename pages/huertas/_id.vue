<template>
  <div>
    <PageHeader 
    :pageTitle="huerta.nombre" 
    :pageName="huerta.nombre" />
    <CausesSingle :data="huerta" />
  </div>
</template>
<script>
export default {
  data(){
    return {
    huerta: {}
    }
  },
  async mounted(){
    await this.$axios.$get('https://admin.pacamama.com.co/huertas/'+ this.$route.params.id).then(response=>{
      this.huerta = response
    })
  }

}

</script>