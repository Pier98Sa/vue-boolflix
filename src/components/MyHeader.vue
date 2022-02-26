<template>
<header>

    <nav class="navbar ms_bg-black">
        <div class="container-fluid ">
            <a class="navbar-brand text-uppercase ms_red fw-bold fs-3">boolflix</a>
            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" >
                <button class="btn ms_btn-bg-red" type="submit">Search</button>
            </form>
        </div>
    </nav>

</header>
  
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>

@import '../style/variables.scss';

.ms_red{
    color: $tertiaryColor;
}

.ms_bg-black{
    background-color: $primaryColor;
}

.ms_btn-bg-red{
    background-color: $tertiaryColor;
    color: $quaternaryColor;
}

</style>