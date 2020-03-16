<template>
    <div>
        <Header title="Vue Playlist"></Header>
        <ul>
          <li v-for="song in songs" v-bind:key ="song" :index="song.name">{{ song.name }} - {{ song.singer }}<button @click="addSong">Add to Playlist</button>
          </li>
        </ul>
        <Footer v-bind:title="title"></Footer>
        <p>{{playlist}}</p>
    </div>
</template>

<script>
// Imports
import Header from './components/Header.vue';
import Footer from './components/Footer.vue';
// import Songs from './components/Songs.vue';
export default {
    components: {
      Header,
      Footer,
    },
    data:function() {
      return {
        songs: [
            {name: 'See You Again', singer: 'Charlie Puth', show: false},
            {name: 'Apologize', singer: 'OneRepbulic', show: false},
            {name: 'Fix You', singer: 'Coldplay', show: false},
            {name: 'Intentions', singer: 'Justin Bieber', show: false},
            {name: 'My heart will go on', singer: 'Celine Dion', show: false},
            {name: 'Pressure', singer: 'Queen', show: false}
        ],
        playlist: [],
      }
    },
    methods:{
      addSong: function(index){
        this.playlist.push(this.songs[index])

      }
    },
   
};
</script>

<style>
body{
    margin: 0;
    font-family: 'Nunito SemiBold';
}
</style>