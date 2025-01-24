<script setup>
import { ref, defineEmits } from "vue";

const text = ref("");
const emits = defineEmits(["onNewItem"]);

function handleSubmit(){
    if(text != ''){
        //llamar a el emit
        emits("onNewItem", text);
        text.value = '';
    }
}

</script>

<template>
<form action="" @submit.prevent="handleSubmit">
    <input type="text" v-model="text">
</form>
</template>

<style scoped>
form{
    margin-bottom: 10px;
}
input{
    width:100%;
    block-size: border-box;
}

</style>