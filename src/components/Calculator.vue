<template>
    <div class="grid">
        <input @keyup.enter="calc()" type="text" v-model="result" placeholder="0">
        <button @:click="input(num)" class="cell num" v-for="num in numbers">{{num}}</button>
        <button @:click="input(op)" class="cell op" v-for="op in operations">{{op}}</button>
        <button @click="reset()" class="cell op">C</button>
        <button @click="calc()" class="cell op eq">=</button>
    </div>
</template>

<script>
    export default {
        name: 'Calculator',
        props: {
            msg: String
        },
        data() {
            return {
               result: '',
               numbers: [1,2,3,4,5,6,7,8,9,0],
               operations: ['+','-','*','/']
            }
        },

        methods: {
            input: function(char){
                this.result = this.result.toString();
                this.result+=char;
            },

            reset: function(){
                this.result = '';
            },

            calc: function(){
                this.result = eval(this.result);
            }
        }
    }
   
</script>

<style lang="scss" scoped>

</style>