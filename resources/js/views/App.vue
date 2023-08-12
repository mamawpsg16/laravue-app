<template>
    <div>
        <button @click="counter+=1">{{ counter }}</button>
        <input type="text" v-model="name">
        {{ helloWorld }}
    </div>
</template>

<script>
    export default {
        data(){
            return{
                counter:0,
                name:null
            }
        },
        computed:{
            helloWorld(){
                return console.log(this.name,'executed');
            }
        },
        methods:{
           
        }
    }
</script>

<style lang="scss" scoped>

</style>