<template>
    <section id="album-container">
        <AlbumCard/>
    </section>
  
</template>

<script>
import axios from 'axios';
import AlbumCard from '@/components/AlbumCard.vue';

export default {
    name: 'Album',
    components: {
        AlbumCard,
    },
    created() {
        axios.get
    }

}
</script>

<style lang="scss" scoped>
    #album-container {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }

</style>