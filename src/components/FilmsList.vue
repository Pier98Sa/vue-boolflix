<template> 
    <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2  ">
        <MyCard v-for="(Film, index) in Films" :key="index" :info="Film" class="col-2 g-4 ms_col-height"/>
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
    .ms_col-height{
        width: 218px;
        height: 342px;
    }
    
</style>