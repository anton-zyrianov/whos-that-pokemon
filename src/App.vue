<template>
  
  <div class="container" v-if="this.start">
    <HeaderApp />
    <div v-if="!this.gameOver">
      <TriesApp :attemps = 'attemps'
      :success = 'success'
      :lifes = 'lifes' />
      <PokemonApp :id="this.id"
      :next="next"
      :data="data" />
      <div v-if="!this.next">
        <InputPokemon @show-pokemon="showPokemon"/>
      </div>

      <div v-else>
        <ButtonNext @next-pokemon="nextPokemon"/>
      </div>

    </div>

    <div v-else>
      <GameOver @restart-game="restartGame" />
    </div>
  </div>

  <div class="container" v-else>
    <HeaderApp />
    <StartGame @start-game="startGame"/>
  </div>

</template>

<script>
import HeaderApp from '../src/components/HeaderApp.vue'
import TriesApp from '../src/components/TriesApp.vue'
import PokemonApp from '../src/components/PokemonApp.vue'
import InputPokemon from '../src/components/InputPokemon.vue'
import GameOver from '../src/components/GameOver.vue'
import ButtonNext from '../src/components/ButtonNext.vue'
import StartGame from '../src/components/StartGame.vue'

export default {
  name: 'App',
  components: {
    HeaderApp,
    TriesApp,
    PokemonApp,
    InputPokemon,
    GameOver,
    ButtonNext,
    StartGame,
  },
  data(){
    return{
      isSuccess: false,
      attemps: 0,
      success: 0,
      lifes: 3,
      gameOver: false,
      next: false,
      start: false,
      data: null,
      id: null,
      res: null,
    }
  },

  async created(){

    this.id = Math.floor(Math.random() * 100);
    console.log(this.id);

      this.res = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.id}/`);
      this.data = await this.res.json();

  },

  methods: {

    async fetchPokemon(){
      this.id = Math.floor(Math.random() * 100);
      console.log(this.id);

      this.res = await fetch(`https://pokeapi.co/api/v2/pokemon/${this.id}/`);
      this.data = await this.res.json();
    },

    showPokemon(name){

      this.attemps++;

      if(name === this.data.name){
        console.log("Nombre introducido es correcto!");
        this.success++;    
        // this.fetchPokemon();
        this.next = true;  
      } else {
        console.log("Nombre introducido no es correcto!");
        this.lifes--; 
        this.noLifes();
      }
    },

    noLifes(){

      if(this.lifes === 0){
        this.gameOver = true;
      }
    },

    nextPokemon(){
      this.fetchPokemon();
      this.next = false;
    },

    restartGame(){
      this.lifes = 3;
      this.gameOver = false;
      this.attemps = 0;
      this.success = 0;

      this.fetchPokemon();
    },

    startGame(){
      this.start = true;
    },
  },
}
</script>

<style>

*{
  margin: 0;
  padding: 0;
  font-family: 'Press Start 2P', cursive;
}

.container{
  background-image: url("../src/assets/img/bg.jpg");
  background-position: center center;
  background-repeat: no-repeat;
  background-size: cover;
  width: 100vw;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-around;

}

</style>
