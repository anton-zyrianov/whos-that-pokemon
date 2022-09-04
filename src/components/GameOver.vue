<template>
   <div class="container-gameover">
      <h1>Game Over!</h1>
      <button class="button" @click="$emit('restart-game')">Restart game</button>
   </div>
</template>

<script>
export default {
   name: 'GameOver',
}
</script>

<style scoped>
   h1{
      color: #fff;
      text-align: center;
   }

   .container-gameover{
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
      background-color: #d92121;
      /* margin: 10px 0; */
      margin-top: 20px;
      max-width: 200px;
      opacity: 0.8;
   }
   
   .button:hover{
      opacity: 1;
   }

</style>