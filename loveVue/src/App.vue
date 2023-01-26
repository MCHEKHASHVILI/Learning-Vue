<script>
export default{
  data(){
    return {
      menuItems: [ "Home", "TOS", "About Us", "Contact" ]
    }
  },
}
</script>
<template>
  <HorizontalMenu :items="menuItems" />
</template>