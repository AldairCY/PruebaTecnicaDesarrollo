<template>
    <div class="row">
        <div class="col-md-6">
        <!--<ul class="list-group">
            <li class="list-group-item" v-for="item in items" :key="item.id">
                $ {{ item.valor }}
            </li>
        </ul>-->
            <div class="card p-5">
                <h5 class="text-center">Total Dinero:</h5><br/>
                <h3 class="text-center">$ {{ totalDineroAcu }} </h3>
            </div>
        </div>
        <div class="col-md-6">
            <div class="card p-3">
                <h5 class="text-center">Dentro de la alcancia hay:</h5><br/>
                <h3 class="text-center">{{ totalMonedas }} monedas</h3>
            </div>
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
            return this.items.reduce((acumulador) => acumulador + Number(1),0)
        }
    }
}
</script>