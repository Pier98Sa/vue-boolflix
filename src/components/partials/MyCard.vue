<template>
  <div>
        <ul class="text-white" >
            <!--poster-->
            <img v-if="info.poster_path" class="img-fluid" :src="'https://image.tmdb.org/t/p/w342/'+ (info.poster_path)" alt="">
            <img v-else class="img-fluid" src="../../assets/not-found.png" alt="">

            <!--nome-->
            <li>{{info.title ? info.title : info.name}}</li>
            <li>{{info.original_title ? info.original_title: info.original_name}}</li>

            <!--Lingua-->
            <div>
                <img class="ms_flag" v-if="languages.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.svg`)" alt="">
                <span v-else>{{info.original_language}}</span>
            </div>

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
    data(){
        return{
            languages: ['en', 'es','fr','hi','it','ja','ko','pt','zh']
        }
    },
    computed:{
        getStar() {
            return Math.ceil(this.info.vote_average / 2);
        }
    }

}
</script>

<style lang='scss' scoped>
    .ms_flag{
        width: 20px;
    }

</style>