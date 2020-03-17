<template>
    <div>
        <Header title="Vue Playlist"></Header>
        <Songs @update="addSong" v-bind:songs="songs"/>
        <Playlist @remove="removeSong" v-bind:playlists="playlists"/>
        <Footer title="Vue Playlist"></Footer>
    </div>
</template>

<script>
// Imports
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Songs from './components/Songs.vue';
import Playlist from './components/Playlist.vue';
export default {
    components: {
      Header,
      Footer,
      Songs,
      Playlist,
    },
    data:function() {
      return {
        songs: [
            {id: 1, name: 'See You Again', singer: 'Charlie Puth'},
            {id: 2, name: 'Apologize', singer: 'OneRepbulic'},
            {id: 3, name: 'Fix You', singer: 'Coldplay'},
            {id: 4, name: 'Intentions', singer: 'Justin Bieber'},
            {id: 5, name: 'My heart will go on', singer: 'Celine Dion'},
            {id: 6, name: 'Pressure', singer: 'Queen'}
        ],
        playlists: [],
      }
    },
    methods: {
      addSong: function(data) {
        console.log(data)
        this.playlists.push(data)
      },
      removeSong: function(index){
        this.playlists.splice(index,1)
      },
   }
   
   
};
</script>

<style>
body{
    margin: 0;
    font-family: 'Nunito SemiBold';
}
</style>