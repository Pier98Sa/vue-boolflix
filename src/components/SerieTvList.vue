<template> 
    <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 ">
        <MyCard v-for="(Serie, index) in Series" :key="index" :info="Serie" class="col g-4"/> 
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

</style>