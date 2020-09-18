<template>
    <div>
        <div class="title">热门推荐</div>
        <ul class="list">
            <li @click="menu1">笔记本电脑</li>
            <li @click="menu2">手机</li>
            <li @click="menu3">键盘</li>
            <li @click="menu4">鼠标</li>
            <li>饮料</li>
            <li>耳机</li>
            <li>零食</li>
            <li>家具</li>
        </ul>
    </div>
</template>
<style>
    .title {
        width: 100px;
        color: red;
    }

    .list li {
        list-style: none;
        width: 100px;
        height: 50px;
        color: chartreuse;
        background-color: white;
        margin-top: 3px;
        line-height: 50px;
        cursor: pointer;
    }
</style>
<script>
    import Msg from './msg.js'

    export default {
        methods: {
            menu1: function () {
                //$emit是用来触发on事件的,(参数名，参数值)
                Msg.$emit('val', '1');
            },
            menu2: function () {
                //$emit是用来触发on事件的,(参数名，参数值)
                Msg.$emit('val', '2');
            },
            menu3: function () {
                //$emit是用来触发on事件的,(参数名，参数值)
                Msg.$emit('val', '3');
            },
            menu4: function () {
                //$emit是用来触发on事件的,(参数名，参数值)
                Msg.$emit('val', '4');
            }

        }
    }
</script>