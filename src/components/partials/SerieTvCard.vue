<template>
  <div>
        <ul class="text-white " v-for="(Serie, index) in Series" :key="index">
            <li>{{Serie.name}}</li>
            <li>{{Serie.original_name}}</li>
            <li v-if="Serie.original_language == 'en'">
                <span class="fi fi-gb"></span>
            </li>
            <li v-else>
                <span  :class="'fi fi-'+ (Serie.original_language) "></span>
            </li>
            <li>{{Serie.vote_average}}</li>
            
             
        </ul>         
  </div>
</template>

<script>
export default {
    name: 'SerieTvCard',
    props:{
        'Series': Array
    }

}
</script>

<style lang='scss' scoped>
@import '~flag-icons/css/flag-icons.css'

</style>