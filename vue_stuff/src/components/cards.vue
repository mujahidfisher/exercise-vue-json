<template>
    <div class="container" v-for="anime in animes" :key="anime.ultimate">
    <div class="card">
        <div class="card-top-img">
            <img class="pic" :src= "anime.img" alt="img-anime-character">
        </div>
        
        <div class="card-character-details">

            <h6 class="character-name" >{{anime.characters}}</h6>

            <h6 class="anime-name">{{anime.anime}}</h6>

            <h6 class="power-level">{{anime.power}}</h6>

            <h6 class="ultimate">{{anime.ultimate}}</h6>
        </div>
    </div>
</div>
</template>

<style>
.pic {
    width: 20rem;
    height: 20rem;
    border-radius: 20px;
    display: flex;
    justify-content: center;
    margin: auto;
    border: 2px black solid;
  }
  
  .card-character-details {
    text-align: center;
    margin-bottom: 100px;
  }
</style>

<script>
// JSON server data
export default {
    data(){
        return{
            animes : []
        }
    },
    mounted() {
        fetch("https://mujahidfisher.github.io/Json_Server/code.json")
        .then(response => response.json())
        .then(data => {
         this.animes = data;
        
          console.log(data);
        }); 
    },
  
}

</script>