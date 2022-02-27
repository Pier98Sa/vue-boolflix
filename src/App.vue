<template>
  <div id="app">
    <MyHeader @search='searching'/>
    <MyMain :searchsResult="listaFilm"/>
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
      searchName : '',
      api:"https://api.themoviedb.org/3/search/movie?api_key=",
      api_key: "facff0615b740fb6db3b6d5e9b22e08f",
      forSearch: "&query=",

    }
  },
  components: {
    MyHeader,
    MyMain
  },
  methods:{
    searching(text){
      this.searchName = text;

      axios.get(this.api + this.api_key + this.forSearch + this.searchName)
      .then((response) => {
        //popolamento dell'array listaAlbum
        this.listaFilm = response.data.results;
        console.log(this.listaFilm);
        this.$emit('films',this.listaFilm);
      });
 
    }

    
  },
}
</script>

<style lang="scss">
@import './style/general.scss';

</style>
