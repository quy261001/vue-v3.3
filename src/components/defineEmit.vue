<template>
    <h1>defineEmit</h1>
    <h2>{{ countValue }}</h2>
    <button @click="() => emit('foo', 123)">clickFoo</button>
    <button @click="() => emit('bar', 'quy', '123', 'ok')">clickFoo</button>
    <button @click="() => emit('count', countValue + 1)">ClickCount</button>
</template>
<script setup lang="ts" generic="count extends number">
import {ref, toRef} from 'vue'
const props = defineProps<{
    countValue: count;
}>()
const countValue = toRef(props, 'countValue')
//AFTER
const emit = defineEmits<{
    foo: [id: number],
    bar: [name: string, ...rest: any[]]
    count: [countValue: Number]
}>()
</script>