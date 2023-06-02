<template>
    <h1>defineEmit</h1>
    <h2>{{ countValue }}</h2>
    <button @click="() => emit('foo', 123)">clickFoo</button>
    <button @click="() => emit('bar', 'quy', '123', 'ok')">clickFoo</button>
    <button @click="() => emit('count', countValue)">ClickCount</button>
</template>
<script setup lang="ts" generic="count extends number">
import {ref} from 'vue'
const countValue = ref(0)
//AFTER
const emit = defineEmits<{
    foo: [id: number],
    bar: [name: string, ...rest: any[]]
    count: [countValue: Number]
}>()
</script>