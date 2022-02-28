<template> 
    <SerieTvCard :Series="searchs" class="col g-4"/>  
</template>

<script>
import SerieTvCard from './partials/SerieTvCard.vue'

export default {
    name:'SerieTvList',
    props:{
        searchs : Array,
    },
    components:{
        SerieTvCard,
    }

}
</script>

<style lang="scss" scoped>

</style>