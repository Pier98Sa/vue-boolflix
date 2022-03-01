<template> 
    <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 ">
        <MyCard v-for="(Film, index) in Films" :key="index" :info="Film" class="col g-4"/>
    </div>
      
</template>

<script>
import MyCard from './partials/MyCard.vue'
export default {
    name:'FilmsList',
    props:{
        Films : Array,
    },
    components:{
        MyCard,
    }

}
</script>

<style lang="scss" scoped>

</style>