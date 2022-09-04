<template>
   <div class="footer">
      <p>© 2022 Anton Zyrianov</p>
      <div class="footer-rrss">
         <a href="https://github.com/anton-zyrianov/whos-that-pokemon"><img src="https://raw.githubusercontent.com/gist/theAdityaNVS/f5b585d1082da2dffffea32434f37956/raw/7f9552d0a179b4f84059259fa878199e369b069c/GitHub-logo.gif" alt="GitHub"></a>
         <a href="https://www.linkedin.com/in/anton-zyrianov/"><img src="http://pixelartmaker-data-78746291193.nyc3.digitaloceanspaces.com/image/0baeb31aedf8e64.png" alt=""></a>
      </div>
   </div>
</template>

<script>
export default {
   name: 'FooterApp',
}
</script>

<style scoped>

   .footer{
      display: flex;
      justify-content: space-around;
      align-items: center;
   }

   p{
      color: #fff;
      margin-top: 30px;
      display: inline-block;
   }

   a:first-child{
      margin-right: 20px;
   }

   img{
      filter: grayscale(100%);
   }

   img:hover{
      filter: grayscale(0%);
   }

   img{
      max-width: 50px;
   }

   @media only screen and (max-width: 747px){
      .footer{
         flex-direction: column;
      }

      p{
         font-size: 10px;
      }

      img{
         max-width: 40px;
      }

      .footer-rrss{
         margin-top: 10px;
      }
   }

</style>