<script>
export default{
    props: {
        item: {
            type: Object,
            required: true
        }
    },
    data(){
        return {
            data1: "pirveli data"
        }
    }
}
</script>
<template>
    <li class="myList" >
        {{ item.title }}
        <button :data-id="item.id"> Delete</button>
    </li>
</template>