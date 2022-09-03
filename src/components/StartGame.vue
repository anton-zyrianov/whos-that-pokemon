<template>
   <div class="container-start">
      <button class="button" @click="$emit('start-game')">Start Game</button>
   </div>
</template>

<script>
export default {
   name: 'StartGame',
}
</script>

<style scoped>

   .container-start{
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 500px;
   }

   .button{
      border-radius: 4px;
      border: 3px solid #000;
      padding: 10px;
      background-color: #fff;
      /* margin: 10px 0; */
      margin-top: 20px;
      max-width: 200px;
      opacity: 0.8;
   }

   .button:hover{
      opacity: 1;
   }

</style>