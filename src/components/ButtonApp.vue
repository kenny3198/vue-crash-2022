<!--eslint-disable-->
<template>
 <button @toggle-add-task="toggle-add-task" @click="onClick()" :style="{ background: color }" class="btn">{{ text}}</button>
  </template>
<!--eslint-disable-->
<script>
export default {
    name: 'ButtonApp',
    props: {
        text: String,
        color: String,
    },
    methods: {
        onClick() {
            this.$emit('btn-click')
        }
    }
}
</script>
<!--eslint-disable-->
<style>

</style>
