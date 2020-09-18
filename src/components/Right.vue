<template>
    <div>
        <div v-if="kk==='1'">
            <GoodList v-bind:goodId="1"/>
        </div>
        <div v-else-if="kk==='2'">
            <GoodList v-bind:goodId="2"/>
        </div>
        <div v-else-if="kk==='3'">
            33333333333333
        </div>
        <div v-else-if="kk==='4'">
            44444444444444
        </div>
        <div v-else>
            <GoodList v-bind:good-id="0"/>
        </div>
    </div>
</template>
<script>
    import Msg from './msg.js'
    import GoodList from './goodList.vue'

    export default {
        data() {
            return {
                kk: 0
            }
        },
        mounted: function () {
            let _this = this;
            //    右侧的this表示当前的意思，_this一般用来表示this的副本。
            Msg.$on('val', function (m) {
                //如果用this，那么这个this指向的是$on
                _this.kk = m;
                //    回调函数，将接受到的val的赋值给变量m处理;
            })
        },
        components: {
            GoodList
        }

    }
</script>