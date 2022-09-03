<template>
   <h1>Who's that Pokémon?</h1>
</template>

<script>
export default {
   name: 'HeaderApp',
}
</script>

<style scoped>

   h1{
      color: #fff;
      /* padding: 20px 0; */
      text-align: center;
   }

   @media only screen and (max-width: 747px){
      h1{
         font-size: 25px;
      }
   }

</style>