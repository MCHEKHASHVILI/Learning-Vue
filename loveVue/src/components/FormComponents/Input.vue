<script setup>
defineEmits(['printText'])
const props = defineProps({
    p: { type: String }

})
const consolee = () => {
    console.log(props.p)
}
</script>
<template>
    <input type="text" class="w-full h-8" :placeholder="p"  @click="printText" />
</template>