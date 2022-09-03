<template>
   
   <div class="next-button">
      <button class="button" @click="$emit('next-pokemon')">Next</button>
   </div>

</template>

<script>
export default {
   name: 'ButtonNext',
}
</script>

<style scoped>

   .next-button{
      display: flex;
      justify-content: center;
   }
   
   .button{
      border-radius: 4px;
      border: 3px solid #000;
      padding: 10px;
      width: 200px;
      background-color: #4fe02d;
      /* margin: 10px 0; */
      margin-top: 20px;
      opacity: 0.8;
   }

   .button:hover{
      opacity: 1;
   }

</style>