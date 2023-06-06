<template>
    <div class="form">
    <div class="form-title">Defina a palavra</div>
    <input type="text"  class="form-input">
    <button>Próximo</button>

    </div >
</template>

<script>
export default{
    name: 'Formulario'
}
</script>

<style>
 .form{
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    justify-content: center;
    margin-top: 20px;
 }

 .form-input{
    padding: 10px 5px;
    border: 0;
    border-radius: 5px;
    margin: 10px 0px;
    text-align: center;
    color: var(--color-text-dark);
    font-size: 16px;
 }


</style>