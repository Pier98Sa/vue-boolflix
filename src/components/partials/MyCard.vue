<template>
  <div>
        <ul class="text-white" >
            <!--poster-->
            <img v-if="info.poster_path" class="img-fluid" :src="'https://image.tmdb.org/t/p/w342/'+ (info.poster_path)" alt="">
            <img v-else src="'https://image.tmdb.org/t/p/w342/movie/940791'" alt="">
            <!--nome-->
            <li>{{info.title ? info.title : info.name}}</li>
            <li>{{info.original_title ? info.original_title: info.original_name }}</li>
            <!--Lingua-->
            <li v-if="info.original_language == 'en'">
                <span class="fi fi-gb"></span>
            </li>
            <li v-else-if="info.original_language == 'ja'">
                <span class="fi fi-jp"></span>
            </li>
            <li v-else-if="info.original_language == 'zh'">
                <span class="fi fi-cn"></span>
            </li>
            <li v-else-if="info.original_language == 'ko'">
                <span class="fi fi-kr"></span>
            </li>
            <li v-else-if="info.original_language == 'hi'">
                <span class="fi fi-in"></span>
            </li>
            <li v-else>
                <span  :class="'fi fi-'+ (info.original_language) "></span>
            </li>
            <!--voto-->
            <div>

                <i v-for="i in 5" :key="i" class="fa-star" :class="(i < getStar) ? 'fa-solid' : 'fa-regular'"></i>

            </div>
            
             
        </ul>         
  </div>
</template>

<script>
export default {
    name: 'MyCard',
    props:{
        'info': Object
    },
    computed:{
        getStar() {
            return Math.ceil(this.info.vote_average / 2);
        }
    }

}
</script>

<style lang='scss' scoped>
    

</style>