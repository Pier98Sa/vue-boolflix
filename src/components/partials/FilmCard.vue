<template>
  <div>
        <ul class="text-white " v-for="(film, index) in films" :key="index">
            <li>{{film.title}}</li>
            <li>{{film.original_title}}</li>
            <li v-if="film.original_language == 'en'">
                <span class="fi fi-gb"></span>
            </li>
            <li v-else>
                <span  :class="'fi fi-'+ (film.original_language) "></span>
            </li>
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
@import '~flag-icons/css/flag-icons.css'

</style>