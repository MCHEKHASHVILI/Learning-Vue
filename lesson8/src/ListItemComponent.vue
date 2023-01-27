<script>
export default {
    props: {
        itemData: { type: Object, required: true }
    },
    mounted(){
        // ...
    }
}
</script>

<template>
    <li><input type="checkbox">{{ itemData.id }} - {{ itemData.name }}</li>
</template>