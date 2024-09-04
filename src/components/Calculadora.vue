<script setup>
import { reactive } from 'vue';

const estado = reactive({
    primeiroNumero: '',
    segundoNumero: '',
    operacoes: {
        soma: (a, b) => a + b,
        subtracao: (a, b) => a - b,
        multiplicacao: (a, b) => a * b,
        divisao: (a, b) => (b !== 0 ? a / b : 'Divisão por zero'),
    },
    resultado: 0,
});

const calcularResultado = () => {
    const { primeiroNumero, segundoNumero, operacaoMatematica } = estado;
    estado.resultado = estado.operacoes[operacaoMatematica](parseFloat(primeiroNumero), parseFloat(segundoNumero));
};
</script>

<template>
    <div class="calculo">
        <input type="number" v-model="estado.primeiroNumero" @input="calcularResultado" />      

        <select v-model="estado.operacaoMatematica" @change="calcularResultado">
            <option value="soma">+</option>
            <option value="subtracao">-</option>
            <option value="multiplicacao">x</option>
            <option value="divisao">/</option>
        </select>
        <input type="number" v-model="estado.segundoNumero" @input="calcularResultado" />

        <p>Resultado: {{ estado.resultado }}</p>
    </div>
</template>

<style scoped>
.calculo {
    text-align: center;
    justify-content: center;
    align-items: center;
}



p {
    color: #efefef;
    margin: 20px auto;
    font-size: 20px;
}


.fnt {
    font-size: 1.2em;
}

input {
    margin: auto;
    padding: 8px;
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 3px;
    display: flex;
    align-items: center;
    text-align: center;

}

select {
    margin: 8px auto;
    padding: 8px;
    width: 300px;
    border: 1px solid #ccc;
    border-radius: 3px;
    display: flex;
    align-items: center;
    text-align: center;


}

</style>