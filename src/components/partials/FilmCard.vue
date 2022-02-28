<template>
  <div>
        <ul class="text-white " v-for="(film, index) in films" :key="index">
            <li>{{film.title}}</li>
            <li>{{film.original_title}}</li>
            <li>{{film.original_language}}</li>
            <li>{{film.vote_average}}</li>
        </ul>         
  </div>
</template>

<script>
export default {
    name: 'FilmCard',
    props:{
        'films': Array
    }

}
</script>

<style lang='scss' scoped>

</style>