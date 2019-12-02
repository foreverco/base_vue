<template>
    <div class='msg'>
        {{msg}}
    </div>
</template>

<script type='text/ecmascript-6'>   
    export default { // 配置对象
        data (){
            return {
                msg:'hello Vue Component'
            }
        }

    }
</script>

<style>
    .msg{
        color:red;
        font-size:30px;
    }
</style>
 