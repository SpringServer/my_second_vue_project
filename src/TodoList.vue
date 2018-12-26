<template>
    <div>
        <div>
            <input type="text" v-model="inputValue">
            <button v-on:click="handsubmit">提交</button>
        </div>
        <ul>
            <todoitem v-for="(item,index) in list" v-bind:key="index" v-text="item" v-bind:index="index" v-on:moveList="spliceIt"></todoitem>
        </ul>
    </div>
</template>
<script>
import list from './components/List'
export default{
    data:function(){
        return {
            inputValue:"",
            list:[]
        }
    },
    methods:{
        handsubmit:function(){
            this.list.push(this.inputValue);
            //console.log(this.list)
            this.inputValue="";
        },
        spliceIt:function(index){
            this.list.splice(index,1)
        },
    },
    components:{
        'todoitem':list
    }
}
</script>

<style>
</style>