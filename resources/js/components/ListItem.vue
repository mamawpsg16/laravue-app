<template>
    <br>
        <span v-if="id == activeId ">-></span>
        <!-- <span v-if="isActive">-></span> -->
        {{ name }}
</template>

<script>
    export default {
        props: ['name','isActive', 'id','activeId'],     

        updated(){
            console.log('updating',     this.name);
        }
    }
</script>
