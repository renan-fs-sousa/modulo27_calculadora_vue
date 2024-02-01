<script setup>
    const props = defineProps(['operacao'])
</script>

<template>
    <form>
        <div class="row">
            <div class="col-sm-4">
                <label class="form-label" for="valor1">Valor 1</label>
                <input :value="operacao.valor1" @input="evento => operacao.valor1 = evento.target.value" class="form-control" type="number" id="numero1" placeholder="Insira um número"/>
            </div>
            <div class="col-sm-4">
                <label class="form-label" for="valor2">Valor 2</label>
                <input :value="operacao.valor2" @input="evento => operacao.valor2 = evento.target.value" class="form-control" type="number" id="valor2" placeholder="Insira um número">
            </div>
            <div class="col-sm-4">
                <label class="form-label" for="select">Operador</label>
                <select :value="operacao.operador" @change="evento => operacao.operador = evento.target.value" class="form-select" id="select">
                    <option value="" selected="selected">Escolha um operador</option>
                    <option value="somar">Somar</option>
                    <option value="subtrair">Subtrair</option>
                    <option value="multiplicar">Multiplicar</option>
                    <option value="dividir">Dividir</option>
                </select>
            </div>
        </div>
    </form>
</template>

<style scoped>
.form-control, 
.form-select {
    margin: 15px 0;   
    text-align: center;

    @media (max-width: 640px) {
        margin: 0 0 30px; 
    }
}
</style>