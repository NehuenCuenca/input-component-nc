<template>
    <div class="wrapper"> 
        <label :for="labelName">{{ labelName }}</label>
        <input type="text" :id="labelName" :placeholder="placeholderInput"/>
    </div>
</template>

<script>
import { Fragment } from 'vue';
export default {
    name: "Input",
    props: {
        labelName: {
            "type": String,
            "required": true,
        },
        placeholderInput: {
            "type": String,
            "required": false,
        }
    },
    components: { Fragment }
}
</script>

<style scoped>
.wrapper {
    display: flex;
    flex-direction: column;
}

label { 
    font: 400 12px 'Noto Sans JP', sans-serif;
    cursor: pointer;
}

input {
    font: 400 14px 'Noto Sans JP', sans-serif;
    border-radius: 8px;
    border: 1px solid var(--InputBorder);
    width: 200px;
    height: 56px;
    padding: 1rem;
}

input:hover, .on-hover input{
    border: 1px solid #333333;
    outline: 1px solid #333333;
}
input:focus, .on-focus input {
    border: 1px solid #2962FF;
    outline: none;
}

</style>