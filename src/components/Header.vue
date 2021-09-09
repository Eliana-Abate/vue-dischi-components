<template>
    <header>
        <div class="container">
            <div class="row">
                <img src="@/assets/images/logo.png"/>
                <GenreFilter/>

            </div>
        </div>
    </header>
  
</template>

<script>
import GenreFilter from '@/components/GenreFilter.vue';

export default {
    name: "Header",
    components: {
        GenreFilter,
    }
}
</script>

<style scoped lang="scss">
    header {
    background-color: #2e3a46;
    height: 70px;
    padding: 10px;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
        .row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 10px;
                img {
                height: 50px;
                }
        }
    
    }
</style>