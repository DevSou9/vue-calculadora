<script setup>

const props = defineProps(['inputNum1', 'inputNum2', 'selectOperacao'])


</script>

<template>

<form>   

<input   @keyup="props.inputNum1" type="number">
<input @keyup="props.inputNum2" type="number">

<select @change="props.selectOperacao">
  <option value="+">+</option>
  <option value="-">-</option>
  <option value="*">*</option>
  <option value="/">/</option>
</select>

</form>

</template>

<style scoped>
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  -webkit-appearance: none;
  margin: 0px;
}

input{
    margin: 20px 6px;
}


</style>