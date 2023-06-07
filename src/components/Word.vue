<template>
       
<div class="word">
  
<div class="word-letters">

    <div class="word-letter" v-for="(letra,key) in palavra" :key="key">
        {{ verificarLetra(letra) || etapa === 'enforcado' ? letra: '' }}
     </div>

</div>

<div class="word-tip">
    {{ dica }}
</div >

    </div >
</template>

<script>

export default{
    name: 'Palavra',
    props:{
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

    }
}
</script>

<style>
 .word{
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
 }

 .word-letters{
    display: flex;
    margin-bottom: 20px;
 }

 .word-letter{
    height: 30px;
    width: 30px;
    margin: 0px 5px;
    border-bottom: 1px solid var(--color-text-light);
    display: flex;
    justify-content: center;
    align-items: center;
 }
</style>