<script setup>
    const props = defineProps(['primeiroNumero', 'segundoNumero', 'filtro', 'selecionarFiltro'])
</script>


<template>
    <form>
        <div class="row mt-5">
            <div class="col-md-2 p-0">
                <input class="form-control" @keyup="$props.primeiroNumero" type="number" placeholder="Digite o primeiro número">
                <div class="col p-0 text-center">
                    <p class="fs-4 m-0" v-if="props.filtro === 'soma'">+</p>
                    <p class="fs-4 m-0" v-else-if="props.filtro === 'subtracao'">-</p>
                    <p class="fs-4 m-0" v-else-if="props.filtro === 'multiplicacao'">*</p>
                    <p class="fs-4 m-0" v-else>/</p>
                </div>
                <input @keyup="props.segundoNumero" class="form-control mb-3" type="number" placeholder="Digite o segundo número">
            </div>
            <div class="col-md-2">
                <select @change="props.selecionarFiltro" class="form-control bg-secondary rounded-3 mb-3">
                    <option value="soma">Soma</option>
                    <option value="subtracao">Subtração</option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="dividir">Divisão</option>
                </select>
            </div>
        </div>
    </form>
</template>