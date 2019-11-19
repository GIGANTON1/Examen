<template>
    <div>
        <h2>Seleccione la Moneda Base</h2>
        <select name="" id="" v-model="moneda" @change="nuevaMonedaSeleccionada"  class="form-control">
            <option value="USD">Dolar Americano</option>
            <option value="AUD">Dolar Australiano</option>
            <option value="CAD">Dolar Canadiense</option>
            <option value="EUR">Euro</option>
            <option value="GBP">Libra Esterlina</option>
        </select>
        <br>
        <h2>Seleccione la Moneda a Convertir</h2>
        <select name="" id="" v-model="moneda" @change="nuevaMonedaSeleccionada"  class="form-control">
            <option value="USD">Dolar Americano</option>
            <option value="AUD">Dolar Australiano</option>
            <option value="CAD">Dolar Canadiense</option>
            <option value="EUR">Euro</option>
            <option value="GBP">Libra Esterlina</option>
        </select>
        <br>
        <form action="" id="formulario-contacto">
            <p>Monto Moneda Base a convertir: {{monto}}</p>
            <input type="text" v-model="monto">
            <br>
            <p>Monto Final Convertido</p>
            <input type="text" v-model="monto" readonly />
        </form>
        <h3>{{moneda}}</h3>
        <h5>{{intercambio}}</h5>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: "ConversionMoneda",
        data:function () {
            return{
                monto: ''
            }
        },
        props:{
            moneda:{
                type: String,
                required: true
            },
            intercambio:{
                type: Number,
                required: true
            }
        },
        methods:{
            nuevaMonedaSeleccionada(){
                axios.get(`https://api.exchangerate-api.com/v4/latest/${this.moneda}`)
                    .then((res) => {
                        this.intercambio = res.data.rates;
                        console.log(res);
                    })
            }
        }
    }
</script>

<style scoped>

</style>