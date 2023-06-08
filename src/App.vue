<script>
import './css/global.css';
import Formulario from './components/form.vue';
import Jogo from './components/game.vue';



export default {
  name: 'App',
  data() {
    return {
      tela: 'inicio',
      etapa: 'palavra',
      palavra: '',
      dica: '',
      erros: 0,
      letras: []
    }
  },
  components: {
    Formulario,
    Jogo
  },
  methods:{
    setPalavra: function(palavra){
      this.palavra = palavra;
      this.etapa = 'dica';
    },

    setDica: function(dica){
      this.dica = dica;
      this.tela = 'jogo';
      this.etapa ='jogo';
    },
    verificarLetra: function(letra){
      return this.letras.find(item => item.toLowerCase() === letra.toLowerCase());
    },

    jogar: function(letra){
      //adiciona letra jogada
      this.letras.push(letra);

      //validar erro 
      this.verificarErros(letra);
    },
    verificarErros: function(letra){
      //acerto
      if(this.palavra.toLowerCase().indexOf(letra.toLowerCase()) >=0){
        return this.verificarAcertos();
      }
      //erros
      this.erros++;

      //enforcado
      if(this.erros === 6){
        this.etapa = 'hanged'
      }
    },
    verificarAcertos: function(){
      let letrasUnicas = [...new Set(this.palavra.split(''))];
      if(letrasUnicas.length === (this.letras.length - this.erros)){
        this.etapa = 'winner';
      }
    },

    jogarNovamente: function(){
      this.palavra = '';
      this.dica = '';
      this.erros = 0;
      this.letras = [];
      this.tela = 'inicio';
      this.etapa = 'palavra';
    }
  }
 }

</script>

<template>
  <header>
    <nav class="navbar">
      <div class="navbar-logo">
          <img src="https://i.imgur.com/LVg7VKM.png" alt="Logo">
      </div>
    </nav>
  </header>
  <main>
    <div id="app">
 <h1>Jogo da Forca</h1>

 <section v-if="tela === 'inicio'" id="inicio">

 <Formulario v-if="etapa === 'palavra'"
 title="Defina a palavra"
 button="Próximo"
 :action="setPalavra"
 />

   <Formulario v-if="etapa === 'dica'"
   title="Defina a dica" 
   button="Iniciar jogo"
   :action="setDica"
   />
 </section>

 <section v-if="tela === 'jogo'" id="jogo">

  <Jogo 
  :erros="erros"
  :palavra="palavra"
  :dica="dica"
  :verificarLetra="verificarLetra"
  :etapa="etapa"
  :letras="letras"
  :jogar="jogar"
  :jogarNovamente="jogarNovamente"
  />
 </section>
 
    </div>
    
  </main>
  <footer class="footer">
    <p>Copyright © Hangman Play 2023. Todos os direitos reservados.</p>
  </footer>



</template>

<style scoped>

.logo {
  display: block;
  margin: 0 auto 2rem;
}

  .header {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }


#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 150px;
}
</style>
