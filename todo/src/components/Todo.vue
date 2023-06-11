<template>

    <h2>{{ ele.item }}</h2>
    <button @click="handleDelete(ele.id)">Delete</button>
</template>

<script setup>

import { defineProps } from 'vue';
defineProps({
    ele:{
        type:Object,
        required:true,
    },
    handleDelete:{
        type:Function,
        required:true,
    }
})
</script>