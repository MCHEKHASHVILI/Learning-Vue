<script>
import ListItem from './ListItem.vue'

export default {
    props: {
        list_data: { type: Array, required: true }
    },
    components: { ListItem }
}
</script>
<template>
    <ul>
        <ListItem v-for="note in list_data" :key="note.index" :item="note" />
    </ul>
</template>