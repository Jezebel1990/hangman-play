<template>
       
<div class="keyboard">

    <button class="keyboard-button" v-for="(letra, key) in 'abcdefghijklmnopqrstuvwxyz'"
    :key="key"
    :disabled="verificarLetra(letra)"
    v-on:click="jogar(letra)"
    >
    {{letra}}
</button>

   </div >
</template>

<script>

export default{
    name: 'Teclado',
    props:{
        letras: Array,
        verificarLetra: Function,
        jogar: Function
     
    },
    data(){
        return {
          
        }
    },
    methods: {
      
    },
    components:{

    }
}
</script>

<style>
 .keyboard{
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    width: 85%;
    margin-top: 20px;
 }
 .keyboard-button{
    margin: 5px;
    text-transform: uppercase;
 }
</style>