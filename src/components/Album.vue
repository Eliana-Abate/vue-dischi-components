<template>
    <section id="album-container">
        <AlbumCard v-for= "(disc, index) in albumByYear()" :key="index" :disc="disc"/>
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
    data(){
        return {
            album: [],
        };
    },
    methods: {
        albumByYear() {
            this.album.sort( (a, b) => {
                return (a.year)-(b.year);
            });

            return this.album;   
        },

    },
    created() {
        
            axios 
            .get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((res) => {
                const response = res.data.response;
                console.log(response);

                this.album = response;   
            })
         
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