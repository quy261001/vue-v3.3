<template>
    <h1>defineSlots</h1>
    <h2>
        <slot msg="'12312'"></slot>
    </h2>
</template>

<script lang="ts" setup>
 const slotValue = defineSlots<{
    default?: (props: { msg: string }) => any
    item?: (props: { id: number }) => any
}>()
</script>