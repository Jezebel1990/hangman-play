<template>
    <div class="game">

        <Hangman
            :erros="erros"/>

        <Word 
            :palavra="palavra"
            :dica="dica"
            :verificarLetra="verificarLetra"
            :etapa="etapa"
            />

    </div >
</template>

<script>
import Hangman from './hangman.vue';
import Word from './word.vue';

export default{
    name: 'Jogo',
    props:{
       erros: Number,
       palavra: String,
       dica: String,
       verificarLetra: Function,
       etapa: String
    },
    data(){
        return {
          
        }
    },
    methods: {
      
    },
    components:{
        Hangman,
        Word
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