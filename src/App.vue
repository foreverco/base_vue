<template>
    <div>
        <img class="logo" src="./assets/logo.png" alt="logo">
        <HelloWorld></HelloWorld>
    </div>
</template>

<script type='text/ecmascript-6'>
    import HelloWorld from './components/HelloWorld.vue'
    export default {
        // 映射组件标签
        components: {
            HelloWorld
        }
    }
</script>

<style>
    .logo{
        width: 200px;
        height :200px;
        border:1px solid red;
    }
</style>
