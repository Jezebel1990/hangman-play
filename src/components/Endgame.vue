<template>
<div class="endgame">

    <div :class="`endgame-text ${etapa}`">
        {{ texto }}
    </div>

    <button class="endgame-button"
    v-on:click="jogarNovamente">Jogar novamente</button>

   </div >
</template>

<script>

export default{
    name: 'Final',
    props:{
        etapa: String,
        texto: String,
        jogarNovamente: Function
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
.endgame-text{
    margin: 20px 0px;
    font-size: 24px;
    font-weight: bold;
}
.endgame-text.hanged{
    color:var(--color-text-error);
}

.endgame-text.winner{
    color:var(--color-text-success);
}
 
</style>