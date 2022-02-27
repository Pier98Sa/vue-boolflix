<template>
  <main>
      <div class="container py-5">
        <div class="row row-cols-xl-5 row-cols-lg-4 row-cols-md-3 row-cols-sm-2 ">
            <div class="col g-4" v-for="(search, index) in searchsResult" :key="index">
                <ul class="text-white">
                    <li>{{search.title}}</li>
                    <li>{{search.original_title}}</li>
                    <li>{{search.original_language}}</li>
                    <li>{{search.vote_average}}</li>
                </ul>
            
            </div>
        

      </div>

      </div>

  </main>
</template>

<script>
export default {
    name: 'MyMain',
    props:{
        searchsResult : Array,
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