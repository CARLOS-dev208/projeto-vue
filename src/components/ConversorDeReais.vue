<template>
<div class="campos">
     <h1>Conversão </h1>
 <span class="p-float-label">
	<InputText id="Reais" type="number" min="1" v-model="reais" />
	<label for="Reais">Reais</label>
</span>
 <span class="p-float-label">
	<InputText id="dolar" type="number"  v-model="dolar" />
	<label for="dolar">dólares</label>
</span>

<div class="actions" >
<Button label="Cálcular" @click="calcular" />
<Button label="Limpar" @click="limpar"/>
</div>
<div class="resultado" v-if="resultado">
    <p>Com {{reais}} reais é possível comprar {{resultado}} dólares a {{dolar}} cada</p>
</div>
</div>
</template>

<script>
export default {
name: "conversor-de-reais",
data(){
	return {
	reais:null,
    dolar:null,
    resultado:null,
	}
},
methods:{
    calcular(){
        this.resultado = (this.reais / this.dolar).toFixed(2)
    },
    limpar(){
        this.resultado = null
        this.reais = null
        this.dolar= null
    }
},

}
</script>

