<template>
    <div>
    {{rt}}
    </div>
</template>

<script>
    export default {
      data(){
          return {
            rt: this.$route.params.id
          }
      },
      head: {
        // if no subcomponents specify a metaInfo.title, this title will be used
        title: 'Default Title',
      }
    }
</script>

<style scoped>

</style>
