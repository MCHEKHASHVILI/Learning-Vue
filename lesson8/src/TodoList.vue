<script>
import ListItemComponent from './ListItemComponent.vue'
export default {
    props: {
        data: { type: Array, required: true }
    },
    components: {
        ListItemComponent
    },
    mounted(){
        // console.log('List Object has been mounted')
    }
}
</script>

<template>
    <ul>
        <ListItemComponent v-for="item in data" :key="item.index" :itemData="item" />
    </ul>
</template>