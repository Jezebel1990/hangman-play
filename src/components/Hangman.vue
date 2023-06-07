<template>
    <div class="hangman">
     <img :src="`${erros}.png`">
       
    </div >
</template>

<script>

export default{
    name: 'Forca',
    props:{
        erros: Number
    },
    data(){
        return {
          
        }
    },
    methods: {
      
    }
}
</script>

<style>
 .hangman img{
    height: 200px;
 }
</style>