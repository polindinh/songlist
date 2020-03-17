<template>
    <div>
        <h1>All Songs</h1>
        <Song v-for="song in songlist" :key="song.id" :id="song.id" :name="song.name" :singer="song.singer" @addSong="addSongToPlaylist" />
    </div>
</template>


<script>
import Song from './Songs.vue'
export default {
    name:'Songlist',
    props:{
     songlist: Array,
    },
    components:{
        Song
    },
    methods:{
        addSongToPlaylist: function(song){
            this.$emit('addSongToList', song);
        }
    }
};
</script>

<style scoped>
</style>