<script setup>
    import { ref, computed } from 'vue';

    const props = defineProps(['operacaoSelecionada','numberA','numberB',])
    const numberA = ref(props.numberA);
    const numberB = ref(props.numberB);
    const operacaoSelecionada = ref(props.operacaoSelecionada);

    const resultado = computed(() => {
        const a = parseFloat(numberA.value);
        const b = parseFloat(numberB.value);

        switch(operacaoSelecionada.value){
            case 'soma':
                return a + b;
            case 'subtracao':
                return a - b;
            case 'multiplicacao':
                return a * b;
            case 'divisao':
                return b !== 0 ? a/b : 'Erro';
            default:
                return 0;
        }
    })
</script>

<template>
    <form class="container justify-content-center">
        <div class="row">
            <input v-model="numberA" type="number" placeholder="Digite o primeiro número">
        </div>
        <div class="row">
            <input v-model="numberB" type="number" placeholder="Digite o segundo número">
        </div>
        <div class="row">
            <output name="resultado" for="number-a number-b">{{ resultado }}</output>
        </div>
        <div class="row mt-3 fw-bold">
            <div class="col-6">
                <label for="operacao" class="p-2">Escolha a operação:</label>
            </div>
            <div class="col-6">
                <select v-model="operacaoSelecionada" name="operacao" class="form-control">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
    form {
        max-width: 500px;
        text-align: center;
    }

    option {
        text-align: center;
    }

    label {
        color: #dff9fb;
    }

    input {
        padding: 10px;
        border: none;
        height: 100px;
        font-size: 32px;
        text-align: end;
        background-color: #dff9fb;
        border-right: 6px solid #FCBA03;
        border-bottom: 2px solid #FCBA03;
        color: #30336b;
    }

    output {
        height: 100px;
        border: none;
        background-color: #dff9fb;
        border-right: 5px solid #FCBA03;
        color: #30336b;
        font-size: 32px;
        text-align: end;
        padding: 10px;
    }
    ::placeholder {
        font-size: 16px;
        color: #000;
    }

    select {
        background-color: #30336b;
        color: #dff9fb;
        cursor: pointer;
    }

    select:focus {
        background-color: #30336b;
        color: #dff9fb;
    }
</style>