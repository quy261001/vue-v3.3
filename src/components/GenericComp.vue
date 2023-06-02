<template>
   <div class="box">
      <h1>Generics</h1>
      <ul>
         <!-- {{ extraProp }} -->
         <li v-for="(item, idx) in items" :key="idx">
            <span v-if="item === selected" style="font-size: large; color: red">{{ item }}</span>
            <span v-else>{{ item }}</span>
         </li>
      </ul>
   </div>
</template>
  
 
<script setup lang="ts" generic="T extends number">
 import type { GenericComp } from './types'

// imported + intersection type
defineProps<GenericComp<T> & {extraProp: string}>()
</script>
 