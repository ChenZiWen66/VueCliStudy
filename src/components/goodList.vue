<template>
    <div name="show">
        <ui class="goodlist">
            <li v-for="goods in list">
                <img v-bind:src="goods.img">
                <p>{{goods.goodName}}</p>
            </li>
        </ui>
    </div>
</template>

<script>
    export default {
        name: "show",
        data() {
            let _this = this;
            let url="";
            if(_this.goodId===1){
                url="json/smartphone.json"
            }else if(_this.goodId===2){
                url="json/Laptop.json"
            }else {
                url="json/Laptop.json"
            }
            this.$http.get(url).then(function (response) {
                _this.list = response.data;
            });
            return {
                list: []
            }
        },
        props:{
            goodId:Number
        },
        watch:{
            goodId(){
                let _this = this;
                let url;
                if(_this.goodId===1){
                    url="json/smartphone.json"
                }else if(_this.goodId===2){
                    url="json/Laptop.json"
                }
                this.$http.get(url).then(function(response){
                    _this.list=response.data
                });
                return {
                    list:[]
                }
            }

        }
    }
</script>

<style>
    .goodlist li {
        list-style: none;
        width: 200px;
        height: 200px;
        float: left;
        font-size: 9px;
        color: red;
        margin-bottom: 30px;
    }
    .goodlist img{
        width: 200px;
        height: 200px;
    }
</style>