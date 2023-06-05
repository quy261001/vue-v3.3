<template>
    <h1>defineOptions</h1>
</template>

<script setup>
import {toRef} from 'vue'
    defineOptions({ inheritAttrs: false })
    // equivalent to ref(1)
    toRef(1)
    // creates a readonly ref that calls the getter on .value access
    toRef(() => props.foo)
    // returns existing refs as-is
    // toRef(existingRef)

    toValue(1) //       --> 1
    toValue(ref(1)) //  --> 1
    toValue(() => 1) // --> 1

</script>