<template>
<div>
  <router-view/>>
  <ul>
    <li><router-link :to="{name: 'list'}">列表</router-link></li>
    <li><router-link :to="{name: 'user'}">用户</router-link></li>
  </ul>
</div>
</template>

<script>
export default {
  name: "Home"
}
</script>

<style scoped>

</style>
