<template>

   <div class="pokemon-form">
      <input type="text" placeholder="Input pokemon name" v-model="namePokemon" required>
      <button class="button" @click.prevent="$emit('show-pokemon', this.namePokemon)">Submit</button>
   </div>

</template>

<script>
export default {
   name: 'InputPokemon',
   data(){
      return{
         namePokemon: '',
      }
   },
}
</script>

<style scoped>

   input{
      border-radius: 4px;
      border: 3px solid #000;
      padding: 10px;
      /* margin: 10px 0; */
   }

   .button{
      border-radius: 4px;
      border: 3px solid #000;
      padding: 10px;
      background-color: #876750;
      /* margin: 10px 0; */
      margin-left: 20px;
      opacity: 0.8;
   }

   .button:hover{
      opacity: 1;
   }

   .pokemon-form{
      display: flex;
      flex-direction: row;
      justify-content: center;
      align-items: center;
   }

   @media only screen and (max-width: 747px){
      .pokemon-form{
         flex-direction: column;
      }

      input{
         margin-bottom: 10px;
      }
   }

</style>