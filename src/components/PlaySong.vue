
<template>
    <div id="songs">
        <ul>
            <li>
                <h2>{{ name }}</h2>
                <p>{{ singer }}</p>
                <p>{{ id }}</p>
                <button @click="remove"> Delete</button>
            </li>
        </ul>
    </div>
</template>
<script>

export default {
    name:'PlaySong',
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
      remove: function(){
        this.$emit('removeSong',{id: this.id, name:this.name, singer:this.singer});
      }
    }
}
</script>
<style scoped>

</style>