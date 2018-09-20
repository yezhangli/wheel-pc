<template>
    <div class="wrapper" :class="{error}">
        <input :value="value" :disabled="disabled" :readonly="readonly" type="text">
        <template v-if="error">
            <icon name="error" class="icon-error"></icon>
            <span class="message-error">{{error}}</span>
        </template>
    </div>
</template>
<script>
    import Icon from './icon'
    export default {
        name:"GuluInput",
        components:{
            Icon,
        },
        props:{
            value:{
                type:String
            },
            disabled:{
                type:Boolean,
                default:false
            },
            readonly:{
                type:Boolean,
                default:false
            },
            error:{
                type:String
            }
        }
    }
</script>
<style lang="scss" scoped>
    $height:32px;
    $boder-color:#999;
    $border-color-hover:#666;
    $border-radius:4px;
    $font-size:12px;
    $box-shadow-color:rgba(0,0,0,0.5);
    $red:#F1453D;
    .wrapper{
        display: inline-flex;
        align-items: center;
        font-size: $font-size;
        > :not(:last-child){
            margin-right:.5em;
        }
        > input {
            height:$height;
            border:1px solid $boder-color;
            border-radius:$border-radius;
            padding: 0 8px;
            font-size: inherit;
            &:hover{
                border-color: $border-color-hover;
            }
            &:focus{
                border-color:inset 0px 1px 3px  $box-shadow-color;
                outline: none;
            }
            &[disabled],
            &[readonly]{
                border-color: #aaa;
                color: #aaa;
                cursor: not-allowed;
            }
        }
        &.error{
            > input{
                border-color: $red;
            }
            .icon-error{
                fill:$red;
            }
            .message-error{
                color: $red;
            }
        }
    }
</style>