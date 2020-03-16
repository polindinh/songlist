<template>
    <div id="songs">
        <ul>
            <li v-for="song in songs" v-bind:key ="song" v-on:click="song.show = !song.show">
                <h2>{{ song.name }}</h2>
                <h3 v-show="song.show">{{ song.singer }}</h3>
                <button v-on:click="deleteSong">Remove from Playlist</button>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    props: {
      songs: {
        type: Array,
        required: true
      }
    },
    data(){
        return{
        }
    },
    methods: {
      deleteSong: function(){
        this.song.pop();
      }
    }
}
</script>
<style scoped>
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
</style>