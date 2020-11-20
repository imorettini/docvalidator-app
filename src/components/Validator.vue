<template>
    <div class="doc-conteiner">
        <form class="form-document">
            <h1>Valide seu CPF</h1>
            <p>Para validar seu documento, digite o número e pressione o botão confirmar.</p>
           <!--<div class="rdb-document">
                <input type="radio" id="rdb-cpf" class="rdb-cpf" name="document" value="cpf" checked>
                <label for="rdb-cpf">CPF</label>
                <input type="radio" id="rdb-cnpj" class="rdb-cnpj" name="document" value="cnpj">
                <label for="rdb-cnpj">CNPJ</label>
            </div> -->
            <div class="input-document">
                <input type="text" class="txt-document" id="cpf" v-model="cpf" maxlength="11" placeholder="Digite o número do CPF" autofocus required>
            </div>
        </form>
        <div class="button-document">
            <button class="btn-confirm" @click="confirm">Confirmar</button>
            <button class="btn-back" v-on:click="backButton()">Voltar</button>
        </div>
    </div>
</template>

<script>
export default {
  data: {
    cpf:''
  },

  methods: {

    backButton(){
    window.location.href = 'https://bit.ly/35MciVX';
    },
  
  	confirm(event){
    	event.preventDefault();
      
      if(!this.validateCpf(this.cpf))
      {
        alert("CPF Inválido :( ");
        
      }else{
      	alert("CPF Válido :) ");
      }
    },
    
  	validateCpf(cpf){
				if((cpf = cpf.replace(/[^\d]/g,"")).length != 11)
    return false

  if (cpf == "00000000000" ||
    cpf == "11111111111" ||
    cpf == "22222222222" ||
    cpf == "33333333333" ||
    cpf == "44444444444" ||
    cpf == "55555555555" ||
    cpf == "66666666666" ||
    cpf == "77777777777" ||
    cpf == "88888888888" ||
    cpf == "99999999999")
    return false;

  var mod;
  var sum = 0;
  var i;

  for (i=1; i<=9; i++)
    sum = sum + parseInt(cpf[i-1]) * (11 - i);

  mod = (sum * 10) % 11;

  if ((mod == 10) || (mod == 11))
    mod = 0;

  if (mod != parseInt(cpf[9]))
    return false;

  sum = 0;

  for (i = 1; i <= 10; i++)
    sum = sum + parseInt(cpf[i-1]) * (12 - i);

  mod = (sum * 10) % 11;

  if ((mod == 10) || (mod == 11))
    mod = 0;

  if (mod != parseInt(cpf[10]))
    return false;

  return true;
}
			}
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto&display=swap');
/* * {
    margin: 0;
    padding: 0;
    border: 0;
} */

body {
    font-family: 'Roboto', sans-serif;
}

.doc-conteiner {
    font-size: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
    width: 524px;
    max-width: 100%;
    color: #555;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
}

.form-document p {
    font-size: 12px;
    margin-bottom: 8px;
}

.rdb-document {
    font-size: 16px;
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-bottom: 8px;
}

.input-document>input {
    border-color: #bbb;
    border-radius: 5px;
    color: #555;
    width: 100%;
    margin-bottom: 8px;
    width: 100%;
    padding: 8px;
    font-size: 16px;
}

.input-document>input:focus {
    border: 1px solid rgba(0, 178, 255, 0.5);
}

.button-document {
    display: flex;
    flex-direction: row;
    align-items: center;
    max-width: 100%;
}

.button-document button {
    cursor: pointer;
    margin: 4px;
    border-radius: 5px;
    flex-grow: 2;
    flex-basis: 50%;
    flex-shrink: 3;
    border-style: none;
    padding: 8px 25px;
}

.button-document .btn-confirm {
    background: #4169E1;
    border-color: transparent;
    color: #FFFFFF;
}

.button-document .btn-confirm:hover {
    cursor: pointer;
    /* background-color: var(--main-color-dark); */
}

.button-document .btn-voltar {
    color: #0A6BC9;
    background: transparent;
    border-color: transparent;
}
</style>