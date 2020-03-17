<template>
    <div id="songs">
        <h1>All Songs</h1>
        <ul>
            <li v-for="song in songs" :key="song.id">

                <h2>{{ song.name }}</h2>
                <p>{{ song.singer }}</p>
                <p>{{ song.id }}</p>
                <button @click="update">Add to Playlist</button>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name:'Songs',
    props: {
      songs: {
        id: Number,
        name:String,
        singer:String,
      }
    },
    
    methods: {
      update: function(){
        this.$emit('update',this.songs);
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
h1{
    text-align: center;
}
</style>