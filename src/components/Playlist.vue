<template>
    <div>
        <h1>Your Playlist</h1>
        <PlaySong v-for="playSong in PlaySonglist" :key="playSong.id" :id="playSong.id" :name="playSong.name" :singer="playSong.singer" @removeSong="removePlaylist" />
    </div>
</template>


<script>
import PlaySong from './PlaySong.vue'
export default {
    name:'PlayList',
    props:{
     PlaySonglist: Array,
    },
    components:{
        PlaySong,
    },
    methods:{
        removePlaylist: function(song){
            this.$emit('removeSongFromPlaylist', song);
        }
    }
};
</script>

<style scoped>

</style>