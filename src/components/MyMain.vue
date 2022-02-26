<template>
  <main>
      <div class="container">

      </div>

  </main>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import '../style/variables.scss';

main{
    background-color: $secondaryColor;
    height: calc(100vh - 68px);
    overflow-y: auto;

    .container{
        max-width: 1280px;
        width: 100%;
        margin: 20px auto;
    }
}

</style> 