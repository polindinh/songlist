<template>
        <ul id="songs">
            <li>
                <h2>{{ name }}</h2>
                <p>{{ singer }}</p>
                <p>{{ id }}</p>
                <button @click="update">Add to Playlist</button>
            </li>
        </ul>
</template>
<script>

export default {
    name:'Song',
    props: {
      id:{
          type:Number,
          required:true,
      },
      name:{
          type: String,
          required: true,
      },
      singer:{
          type:String,
          required:true,
      }
    },
    
    methods: {
      update: function(){
        this.$emit('addSong',{id: this.id, name:this.name, singer:this.singer});
      }
    }
}
</script>
<style scoped>
    button{
        background-color: #1DA1F2;
        padding:5px 10px;
        color: white;
        border-radius: 10px;

    }

</style>