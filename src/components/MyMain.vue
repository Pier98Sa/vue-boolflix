<template>
  <main>
      <div class="container py-5">
            <h3 v-if="searchsFilm.length > 0" class="text-white">Films:</h3>
            <FilmsList  :Films="searchsFilm"/>
            
            <h3 v-if="searchsSerieTv.length > 0" class="text-white">Serie Tv:</h3>
            <SerieTvList :Series="searchsSerieTv"/>
      </div>
  </main>
</template>

<script>

import FilmsList from "./FilmsList.vue"
import SerieTvList from "./SerieTvList.vue"

export default {
    name: 'MyMain',
    props:{
        searchsFilm : Array,
        searchsSerieTv :  Array
    },
    components:{
        FilmsList,
        SerieTvList,  
    }

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

main{
    background-color: $secondaryColor;
    height: calc(100vh - 68px);
    overflow-y: auto;
}

</style> 