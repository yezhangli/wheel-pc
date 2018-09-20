<template>
    <div>
        <div class="box">
            <g-input value="zhangsan" disabled></g-input>
            <g-input value="zhangsan" readonly></g-input>
            <g-input value="zhangsan"></g-input>
        </div>
        <div class="box">
            <g-input value="zhangsan" error="姓名不能少于2个字"></g-input>
        </div>
        <div class="box">
            <g-button :loading="loading1" @click="loading1 = !loading1">我爱JS</g-button>
            <g-button icon="settings">我爱JS</g-button>
            <g-button icon="right" icon-position="right">我爱JS</g-button>
            <g-button-group>
                <g-button icon="left">上一页</g-button>
                <g-button>更多</g-button>
                <g-button icon="right" icon-position="right">下一页</g-button>
            </g-button-group>
        </div>
    </div>
</template>

<script>
    export default {
        
    }
</script>

<style scoped>

</style>