<template>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Validador de CPF e CNPJ</title>
    <link rel="stylesheet" type="text/css" href="style.css">
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">
</head>

<body>
    <div class="doc-conteiner">
        <form class="form-document">
            <h1>Valide seu CPF/CNPJ</h1>
            <p>Para validar seu documento, selecione entre as opções CPF ou CNPJ, digite o número e pressione o botão confirmar.</p>
            <div class="rdb-document">
                <input type="radio" id="rdb-cpf" class="rdb-cpf" name="document" value="cpf" checked>
                <label for="rdb-cpf">CPF</label>
                <input type="radio" id="rdb-cnpj" class="rdb-cnpj" name="document" value="cnpj">
                <label for="rdb-cnpj">CNPJ</label>
            </div>
            <div class="input-document">
                <input type="text" id="txt-document" maxlength="14" placeholder="Digite o número do documento" autofocus>
            </div>
        </form>
        <div class="button-document">
            <button class="btn-confirm">Confirmar</button>
            <button class="btn-back">Voltar</button>
        </div>
    </div>
    <script src="docValidator.js"></script>
    <!-- <script src="https://cdn.jsdelivr.net/npm/vue@2.6.12/dist/vue.js"></script> -->
</body>
</html>
</template>

<script>
export default {
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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