
<template>
  <h1>Vue 3.3</h1>
  <div class="main">
      <!-- <GenericCompVue :items ="['123', 2, 3, 5]" :selected = "'123'" :extraProp="123"/> -->
      <!-- <defineEmit :countValue="countValue"  @foo = "clickFoo" @bar = "clickBar" @count = "clickCount"/> -->
      <!-- <defineSlot>123213</defineSlot> -->
      <!-- <experimental :title="title"></experimental> -->
      <!-- <defineModel :modelValue="modelValue" @update:modelValue="handleModel"></defineModel> -->
      <defineOptions></defineOptions>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import GenericCompVue from './components/GenericComp.vue'
import defineEmit from './components/defineEmit.vue';
import defineSlot from './components/defineSlot.vue';
import experimental from './components/experimental.vue';
import defineModel from './components/defineModel.vue';
import defineOptions  from './components/defineOptions.vue';

const countValue = ref(0)
const title = ref('quy')
const modelValue = ref('model')

const clickFoo = (value: any) => {
  console.log(value)
}
const clickBar = (value: any) => {
  console.log(value)
}
const clickCount = (value: any) => {
  countValue.value = value
}
const handleModel = (value: any) => {
  modelValue.value = value;
}
</script>

<style scoped>
header {
line-height: 1.5;
max-height: 100vh;
}

.logo {
display: block;
margin: 0 auto 2rem;
}

nav {
width: 100%;
font-size: 12px;
text-align: center;
margin-top: 2rem;
}

nav a.router-link-exact-active {
color: var(--color-text);
}

nav a.router-link-exact-active:hover {
background-color: transparent;
}

nav a {
display: inline-block;
padding: 0 1rem;
border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
border: 0;
}

@media (min-width: 1024px) {
header {
  display: flex;
  place-items: center;
  padding-right: calc(var(--section-gap) / 2);
}

.logo {
  margin: 0 2rem 0 0;
}

header .wrapper {
  display: flex;
  place-items: flex-start;
  flex-wrap: wrap;
}

nav {
  text-align: left;
  margin-left: -1rem;
  font-size: 1rem;

  padding: 1rem 0;
  margin-top: 1rem;
}
}
</style>
