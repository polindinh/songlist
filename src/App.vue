<template>
    <div id="container">
        <Header title="Vue Playlist"></Header>
        <div id="content">
          <Songlist v-bind:songlist="songs" @addSongToList="addToPlaylist"/>
          <PlayList v-bind:PlaySonglist="playlists" @removeSongFromPlaylist="removeSong"/>
        </div>
        <Footer title="Vue Playlist"></Footer>
    </div>
</template>

<script>
// Imports
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
import Songlist from './components/Songlist.vue';
import PlayList from  './components/PlayList.vue';

export default {
    name: "App",
    components: {
      Header,
      Footer,
      Songlist,
      PlayList,
    },
    data: function(){
      return {
        songs: [
            {id: 1, name: 'See You Again', singer: 'Charlie Puth'},
            {id: 2, name: 'Apologize', singer: 'OneRepbulic'},
            {id: 3, name: 'Fix You', singer: 'Coldplay'},
            {id: 4, name: 'Intentions', singer: 'Justin Bieber'},
            {id: 5, name: 'My heart will go on', singer: 'Celine Dion'},
            {id: 6, name: 'Pressure', singer: 'Queen'},
        ],
        playlists: [],
      }
    },
    methods: {
      addToPlaylist: function(song) {
        console.log(song)
        var index ;
        for(index = 0; index < this.songs.length; index++){
          if(song.id == this.songs[index].id){
            this.playlists.push(this.songs[index]);
            this.songs.splice(index,1);
            break;
          }
        }
      },
      removeSong: function(song){
        console.log(song)
        var index ;
        for(index = 0; index < this.playlists.length; index++){
          if(song.id == this.playlists[index].id){
            this.songs.push(this.playlists[index]);
            this.playlists.splice(index,1);
            break;
          }
        }
      },

   }
   
   
};
</script>

<style>
body{
    margin: 0;
    font-family: 'Nunito SemiBold';
}

#songs{
    width: 100%;
    max-width: 1200px;
    margin: 40px auto;
    padding: 0 20px;
    box-sizing: border-box;
}
ul{
    display: flex;
    flex-wrap: wrap;
    list-style-type: none;
    padding: 0;
}
li{
    flex-grow: 1;
    flex-basis: 300px;
    text-align: center;
    padding: 30px;
    border: 1px solid #222;
    margin: 10px;
}
h1{
    text-align: center;
}
#content{
  display: grid;
  grid-template-columns: 1fr 1fr;
  width:70vw;
  margin:auto;
}

</style>