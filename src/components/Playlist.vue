<template>
    <div id="songs">
        <h1>Your Playlist</h1>
        <ul>
            <li v-for="song in playlists" :key="song.id">
                <h2>{{ song.name }}</h2>
                <p>{{ song.singer }}</p>
                <button @click="deleteSong">Remove</button>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    name:'Playlist',
    props:{
     playlists: {
        type: Array,
      },
    },
    data(){
        return{
        }
    },
    methods:{
        deleteSong: function(){
            this.$emit('remove');
        }
    }
};
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
h1{
    text-align: center;
}
</style>