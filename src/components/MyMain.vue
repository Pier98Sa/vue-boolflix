<template>
  <main>
      <div class="container py-5">
        <FilmsList class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 " :searchs="searchsResult"/>

      </div>

  </main>
</template>

<script>

import FilmsList from "./FilmsList.vue"
export default {
    name: 'MyMain',
    props:{
        searchsResult : Array,
    },
    components:{
        FilmsList
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