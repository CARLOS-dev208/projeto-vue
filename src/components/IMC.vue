<template>
        <div class="campos">
        <h1>Cálcular IMC</h1>
      <span class="p-float-label">
        <InputText id="peso" type="number"  v-model="weight" :disabled="imc"/>
        <label for="peso">Peso</label>
      </span>
      <span class="p-float-label">
        <InputText id="altura" type="number"  v-model="height" :disabled="imc"/>
        <label for="altura">Altura</label>
      </span>
      <div class="actions">
      <Button label="Cálcular" @click="calcular" :disabled="imc"/>
      <Button label="Limpar" @click="limpar"/>
      </div>
      <div v-if="imc">
        <p>Seu IMC é: {{imc}}</p>
        <p>A classificação do seu IMC é: {{classificacao}}</p>
      </div>
      </div>
</template>

<script>
export default {
  name: 'IMC',
    data(){
    return{
      height: null,
      weight:null,
      imc:null,
      classificacao:"",
    }
  },
  methods:{
    calcular(){
      this.imc = (this.weight / (this.height * this.height)).toFixed(2);
      if(this.imc < 18.5){
        this.classificacao = "Magreza"
      }else if(this.imc >= 18.5 && this.imc < 25){
        this.classificacao = "Normal"
      }else if(this.imc >=25 && this.imc < 30){
        this.classificacao = "Sobrepeso"
      }else if(this.imc >=30 && this.imc <40){
        this.classificacao = "Obesidade"
      }else{
        this.classificacao = "Obesidade Grave"
      }
    },
    limpar(){
      this.height= null,
      this.weight=null,
      this.imc=null,
      this.classificacao=""
    }
  }
}
</script>