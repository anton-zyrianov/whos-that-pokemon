<template>

   <div class="pokemon-box">
      <img :class="!next ? 'filter-on' : ''" :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/other/home/${id}.png`" alt="Pokemon Image">
      <p class="pokemon-name" v-if="!next">???</p>
      <p class="pokemon-name" v-else>{{ data.name }}</p>
   </div>

</template>

<script>
export default {
   name: 'PokemonApp',
   props: {
      id: Number,
      next: Boolean,
      data: Object,
   },
}
</script>

<style scoped>

   .pokemon-box{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin-top: 40px;
      margin-bottom: 50px;
   }

   .pokemon-name{
      color: #fff;
      text-align: center;
      font-size: 40px;
      margin-top: 20px;
   }

   img{
      max-width: 300px;
      image-rendering: pixelated;
      /* border-radius: 100%; */
      animation: movement 2s linear infinite;
   }

   @keyframes movement{
      0% {
         transform: translateY(0);  
      }
      
      25% {
         transform: translateY(-5px);
      }

      50% {
         transform: translateY(0);
      }

      75% {
         transform: translateY(5px);
      }

      100% {
         transform: translateY(0);
      }
   }

   @media only screen and (max-width: 747px){
      img{
         max-width: 200px;
      }

      .pokemon-name{
         font-size: 25px;
      }
   }

   .filter-on {
      filter: brightness(0);
   }

</style>