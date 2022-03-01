<template>
  <div id="app">
    <MyHeader @search='doSearch'/>
    <MyMain :searchsFilm="listaFilm" :searchsSerieTv="listaSerieTv"/>
  </div>
</template>

<script>
const axios = require('axios');

import MyHeader from './components/MyHeader.vue'
import MyMain from './components/MyMain.vue'

export default {
  name: 'App',
  data(){
    return{
      listaFilm: [],
      listaSerieTv: [],
      api_key: "facff0615b740fb6db3b6d5e9b22e08f",
      language: 'it-It',

    }
  },
  components: {
    MyHeader,
    MyMain
  },
  methods:{
    doSearch(text){

      const params = {
        params:{
          'api_key': this.api_key,
          'query': text,
          'language': this.language
        }
       
      }

      this.searchingFilm(params);
      this.searchingSerieTv(params)
    },

    searchingFilm(params){
      axios.get('https://api.themoviedb.org/3/search/movie', params)
      .then((response) => {
        //popolamento dell'array listaAlbum
        this.listaFilm = response.data.results;
        console.log(this.listaFilm);
        this.$emit('films',this.listaFilm);
      });
    },

    searchingSerieTv(params){
      axios.get('https://api.themoviedb.org/3/search/tv', params)
      .then((response) => {
        //popolamento dell'array listaAlbum
        this.listaSerieTv = response.data.results;
        console.log(this.listaSerieTv);
        this.$emit('serieTv',this.listaSerieTv);
      });
    }


    
  },
}
</script>

<style lang="scss">
@import '~@fortawesome/fontawesome-free/css/all.css';
@import './style/general.scss';
@import '~flag-icons/css/flag-icons.css'

</style>
