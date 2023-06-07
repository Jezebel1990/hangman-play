<template>
    <div class="game">

        <Hangman
        :erros="erros"/>

        <Word />
    </div >
</template>

<script>
import Hangman from './hangman.vue';
import Word from './word.vue';

export default{
    name: 'Jogo',
    props:{
       erros: Number
    },
    data(){
        return {
          
        }
    },
    methods: {
      
    },
    components:{
        Hangman
    }
}
</script>

<style>
.game{
    width: 100%;
    display: flex;
    flex-direction: column;
    text-align: center;
}
 
</style>