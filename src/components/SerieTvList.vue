<template> 
    <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 ">
        <MyCard v-for="(Serie, index) in Series" :key="index" :info="Serie" class="col-2 g-4 ms_col-height"/> 
    </div>
     
</template>

<script>
import MyCard from './partials/MyCard.vue'
export default {
    name:'SerieTvList',
    props:{
        Series : Array,
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