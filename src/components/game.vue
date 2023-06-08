<template>
    <div class="game">

        <Hangman
            :erros="erros"
            />

        <Word 
            :palavra="palavra"
            :dica="dica"
            :verificarLetra="verificarLetra"
            :etapa="etapa"
            />

            <Keyboard
                v-if="etapa === 'jogo'"
                :letras="letras"
                :verificarLetra="verificarLetra"
                :jogar="jogar"
                />

            <Endgame 
                v-if="etapa != 'jogo'"
                :etapa="etapa"
                :texto="etapa === 'winner' ? 'Parabéns!' : 'Tadinho :('"
                :jogarNovamente="jogarNovamente"
                />
    </div >
</template>

<script>
import Hangman from './Hangman.vue';
import Word from './Word.vue';
import Keyboard from './Keyboard.vue';
import Endgame from './Endgame.vue';

export default{
    name: 'Jogo',
    props:{
       erros: Number,
       palavra: String,
       dica: String,
       verificarLetra: Function,
       etapa: String,
       letras: Array,
       jogar: Function,
       jogarNovamente: Function
    },
    data(){
        return {
          
        }
    },
    methods: {
      
    },
    components:{
    Hangman,
    Word,
    Keyboard,
    Endgame
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
