
<template>
  <div class="my-3 flip-container" @mouseover="overChangeShow" @mouseleave="leaveChangeShow">
      <transition name="fade" mode="out-in">

        <div v-if="show == true" class="front">
            <!--poster-->
            <img v-if="info.poster_path" class="poster-img" :src="'https://image.tmdb.org/t/p/w342/'+ (info.poster_path)" alt="">
            <img v-else  class="poster-img" src="../../assets/movie.jpg" alt="">
        </div>
            
        
        <div v-else class="back text-white p-3" >
            
            <!--nome-->
            <div>{{info.title ? info.title : info.name}}</div>
            <div>{{info.original_title ? info.original_title: info.original_name}}</div>

            <!--Lingua-->
            <div>
                <img class="ms_flag" v-if="languages.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.svg`)" alt="">
                <span v-else>{{info.original_language}}</span>
            </div>

            <!--voto-->
            <div> <i v-for="i in 5" :key="i" class="fa-star" :class="(i < getStar) ? 'fa-solid' : 'fa-regular'"></i></div>
            <!--Riassunto-->
            <div class="resume">
                {{info.overview}}
            </div>
                
        </div> 

    </transition>
                
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
            languages: ['en', 'es','fr','hi','it','ja','ko','pt','zh'],
            show: true
        }
    },
    methods:{
        overChangeShow(){
            this.show = false
        },
        leaveChangeShow(){
            this.show = true
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
@import '../../style/variables.scss';
    .ms_flag{
        width: 20px;
    }
    .flip-container{
        position: relative;
        
        .front,
        .back {
            height: 342px;
            width: 100%;
            position: absolute;
            left: 0;
            top: 0;
            overflow: auto;
            background-color: $primaryColor;
        }
        .poster-img{
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
    }
    
    
</style>