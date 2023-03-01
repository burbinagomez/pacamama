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
    await this.$axios.$get('https://admin.pacamama.com.co/api/huertas/'+ this.$route.params.id + '?populate=media').then(response=>{
      console.log(response)
      this.huerta = response.data.attributes
    })
  }

}

</script>