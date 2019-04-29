<template>
  <div class="info">
    <h1>This is an about info</h1>
    <button type="button" @click="add()">添加</button>
  </div>
</template>

<script>
import store from '@/store'
export default {
    name: "info",
    store,
    methods: {
        add(){
            console.log("add event from info")
            store.commit("increase")
        }
    },
}
</script>

