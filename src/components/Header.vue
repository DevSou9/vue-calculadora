<script setup>

const props = defineProps(['resultado', 'num1', 'num2'])
</script>





<template>
<header>
    <h1>Calculadora VueJS</h1>

    <div v-if="props.num1 !== null && props.num2 !== null && !isNaN(props.resultado)">
  <h2> {{ props.resultado }}</h2>
</div>

    
  
  </header>

</template>

<style scoped>
header{
  max-width: 500px;
}

h1{
  text-align: center;
}
div{
  margin-top: 15px;
  background-color: black;
  color: #fff;
  
  width: 500px;
  text-align: center;
}

</style>
