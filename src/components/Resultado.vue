<script setup>
    const props = defineProps(['filtro', 'funcaoSoma', 'funcaoSub', 'funcaoMult', 'funcaoDiv'])
</script>

<template>
    <div class="row"> 
        <div class="col d-flex align-items-center justify-content-center">
            <p class="m-0 me-2">resultado =</p>
            <div class="border border-secondary rounded-3">
                <p class="m-0 p-2 fw-bold" v-if="props.filtro === 'soma'"> {{ props.funcaoSoma }}</p>
                <p class="m-o p-2 fw-bold" v-else-if="props.filtro === 'subtracao'"> {{ props.funcaoSub }}</p>
                <p class="m-0 p-2 fw-bold" v-else-if="props.filtro === 'multiplicacao'"> {{ props.funcaoMult }}</p>
                <p class="m-0 p-2 fw-bold" v-else> {{ props.funcaoDiv }}</p>
            </div>
        </div>
    </div>
</template>