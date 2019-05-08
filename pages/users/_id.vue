<template>
    <div>
      I am id component and my id is {{this.$route.params.id}}
    </div>
</template>

<script>
    export default {
      name: "_id",

      // NUXT-SPECIFIC feature "validate"  to make sure only valid dynamic url segments reach a specific url
      // validate should return true
      validate(data){
        //  1) A page will only load if the id is "1", otherwise, page is not found
        // return data.params.id == 1

        // 2)  A page will load only load if id is a number
        return /^\d+$/.test(data.params.id) //will  return true if id is a number
      }
    }


</script>

<style scoped>

</style>
