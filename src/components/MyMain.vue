<template>
  <main>
      <div class="container py-5">
        <div v-if="searchsFilm.length > 0">
            <h3 class="text-white">Films:</h3>
        </div>
        <FilmsList class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 " :searchs="searchsFilm"/>
        
        <div v-if="searchsSerieTv.length > 0">
            <h3 class="text-white">Serie Tv:</h3>
        </div>
        <SerieTvList class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 " :searchs="searchsSerieTv"/>

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