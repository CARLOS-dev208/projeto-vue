<template>
<div class="tela">
<IMC />
<ConversorDeReais/>
</div>

</template>

<script>
import ConversorDeReais from "./components/ConversorDeReais.vue";
import IMC from "./components/IMC";
export default {
  name: 'App',
  components: {
   ConversorDeReais,
   IMC
  },

}
</script>


