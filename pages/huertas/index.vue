<template>
  <div>
    <PageHeader pageTitle="Huertas" pageName="Huertas" />
    <CausesGrid :causes="huertas" />
  </div>
</template>
<script>
export default {
  data (){
    return {
      huertas: []
    }
  },
  async mounted(){
    await this.$axios.$get('https://admin.pacamama.com.co/api/huertas?populate=media').then(response=>{
      this.huertas = response.data
    })
  }
}

</script>