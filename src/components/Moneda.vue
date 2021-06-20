<template>
<div>
    <div class="card my-5">
        <div class="card-body">
            <div align="center">
                <img :src="moneda.imagen" width="150" height="140">
            </div>
            <button v-on:click="agregarMoneda(moneda)" class="btn btn-primary form-control">Introducir Moneda</button>        
        </div>
    </div>
</div>
</template>

<script>

export default {
    name: 'Moneda',
    props:['moneda'],
    methods: {
        agregarMoneda(moneda){
            this.$emit('agregar-moneda', moneda);
        }
    }
}
</script>