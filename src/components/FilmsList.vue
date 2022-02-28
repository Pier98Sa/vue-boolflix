<template>
  
    <FilmCard :films="searchs" class="col g-4"/>  
   
</template>

<script>
import FilmCard from './partials/FilmCard.vue'
export default {
    name:'FilmsList',
    props:{
        searchs : Array,
    },
    components:{
        FilmCard,
    }

}
</script>

<style lang="scss" scoped>

</style>