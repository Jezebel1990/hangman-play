<template>
<div class="endgame">

    <div :class="`endgame-text ${etapa}`">
        {{ texto }}
    </div>

    <button class="endgame-button">Jogar novamente</button>

   </div >
</template>

<script>

export default{
    name: 'Final',
    props:{
        etapa: String,
        texto: String
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