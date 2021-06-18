<template>
    <div>
        <ul class="list-group">
            <li class="list-group-item" v-for="item in items" :key="item.id">
                $ {{ item.valor }}
            </li>
        </ul>
        <div class="card p-4 my-5">
            <h4 class="text-center">Total Dinero: $ {{ totalDineroAcu }} </h4>
        </div>
        <div class="card p-4 my-5">
            <h4 class="text-center">Dentro de la alcancia hay: {{ totalMonedas }} monedas</h4>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Alcancia',
    props: ['items'],
    computed: {
        totalDineroAcu(){
            return this.items.reduce((acumulador,item) => acumulador + Number(item.valor),0)
        },
        totalMonedas(){
            return this.contador++
        }
    }
}
</script>