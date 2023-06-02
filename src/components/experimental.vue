<template>
    <h1>Experimental Features
    <h2>{{ title }}</h2>
</h1>
</template>
<script lang="ts" setup>
import { watchEffect } from 'vue';

const { msg = 'hello', title = '123' } = defineProps(['msg', 'title'])

watchEffect(() => {
  // accessing `msg` in watchers and computed getters
  // tracks it as a dependency, just like accessing `props.msg`
  console.log(`msg is: ${msg}`)
})
</script>
