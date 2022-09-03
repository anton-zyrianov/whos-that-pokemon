<template>
   <div class="try-box">
      <p class="box-attemps">Attemps: {{ attemps }}</p>
      <p class="box-success">Success: <span>{{ success }}</span></p>
      <p class="box-failed">Lifes: <span>{{ lifes }}</span></p>
   </div>
</template>

<script>
export default {
   name: 'TriesApp',
   props: {
      attemps: Number,
      success: Number,
      lifes: Number,
   }
}
</script>

<style scoped>

   .try-box{
      background-color: #000;
      border: 6px solid #fff;
      padding-top: 10px;
      padding-bottom: 10px;
      max-width: 200px;
      margin: 0 auto;
      border-image: url("data:image/svg+xml;charset=utf-8,%3Csvg width='100' height='100' viewBox='0 0 100 100' fill='none' xmlns='http://www.w3.org/2000/svg'%3E %3Cstyle%3Epath%7Banimation:stroke 5s infinite linear%3B%7D%40keyframes stroke%7Bto%7Bstroke-dashoffset:776%3B%7D%7D%3C/style%3E%3ClinearGradient id='g' x1='0%25' y1='0%25' x2='0%25' y2='100%25'%3E%3Cstop offset='0%25' stop-color='%232d3561' /%3E%3Cstop offset='25%25' stop-color='%23c05c7e' /%3E%3Cstop offset='50%25' stop-color='%23f3826f' /%3E%3Cstop offset='100%25' stop-color='%23ffb961' /%3E%3C/linearGradient%3E %3Cpath d='M1.5 1.5 l97 0l0 97l-97 0 l0 -97' stroke-linecap='square' stroke='url(%23g)' stroke-width='3' stroke-dasharray='388'/%3E %3C/svg%3E ") 1;
   }

   .box-attemps{
      color: #fff;
      text-align: center;
   }

   .box-success{
      color: #31dd00;
      text-align: center;
   }

   .box-failed{
      color: #f50000;
      text-align: center;
   }

   span{
      color: #fff;
   }
   
   p{
      margin-bottom: 10px;
   }

   p:last-child{
      margin-bottom: 0;
   }

</style>