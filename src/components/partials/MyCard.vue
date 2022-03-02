<template>
    <div class="flip-box my-3 ">
        <div class="flip-box-inner">

            <div class="flip-box-front">
                <!--Poster-->
                <img v-if="info.poster_path" class="poster-img" :src="'https://image.tmdb.org/t/p/w342/'+ (info.poster_path)" alt="">
                <img v-else  class="poster-img" src="../../assets/movie.jpg" alt="">
            </div>

            <div class="flip-box-back p-1">
                <!--Titolo-->
                <div> <span class="fw-bolder">Titolo: </span>  {{info.title ? info.title : info.name}}</div>
                <div><span class="fw-bolder">Titolo originale: </span> {{info.original_title ? info.original_title: info.original_name}}</div>

                <!--Lingua-->
                <div>
                    <img class="ms_flag" v-if="languages.includes(info.original_language)" :src="require(`../../assets/flags/${info.original_language}.svg`)" alt="">
                    <span v-else>{{info.original_language}}</span>
                </div>

                <!--Valutazione-->
                <div> <span class="fw-bolder">Voto: </span>   <i v-for="i in 5" :key="i" class="fa-star" :class="(i < getStar) ? 'fa-solid' : 'fa-regular'"></i></div>

                <!--Riassunto-->
                <div class="resume">
                   <span class="fw-bolder">Overview: </span>  {{info.overview}}
                </div>
            </div>
        </div>
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
    .flip-box {
        background-color: transparent;
        height: 100%;
        width: 100%;
        perspective: 1000px;

        

        .flip-box-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 1s;
            transform-style: preserve-3d;

            .flip-box-front, .flip-box-back {
                position: absolute;
                width: 100%;
                height: 100%;
                -webkit-backface-visibility: hidden;
                backface-visibility: hidden;
            }

            .flip-box-back {
                background-color: $primaryColor;
                color: $quaternaryColor;
                transform: rotateY(180deg);
                overflow: auto;
            }

            .ms_flag{
                width: 20px;
            }

            .poster-img{
                width: 100%;
                height: 100%;
                object-fit: cover;
            }
            
        }
    }

    .flip-box:hover .flip-box-inner {
        transform: rotateY(180deg);
    }
  
</style>