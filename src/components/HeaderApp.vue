<!--eslint-disable-->
<template>
<header>
<h1>{{ title }}</h1>
<ButtonApp @btn-click="$emit('toggle-add-task')"
 :text="showAddTask ? 'close' : 'Add task'
 " :color="showAddTask ? 'red' : 'green'"/>
</header>
</template>
<!--eslint-disable-->
<script>
import ButtonApp from './ButtonApp'
export default {
 name: 'HeaderApp',
    props:{
        title: String,
        showAddTask: Boolean
    },

    components: {
        ButtonApp,
    }
}
    

</script>
<!--eslint-disable-->
<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    font-size: 10px;
}
</style>
