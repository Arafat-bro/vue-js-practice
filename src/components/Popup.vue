<template>
    <div v-show="false">
        <h2>This is Popup</h2>
        <input type="text" name="" id="" v-model="name">
        <button @click="$emit('close',name)">Close Popup</button>
    </div>
</template>

<script>

    export default {
        name: 'Popup',
        // emits:['close'],
        emits:{
            close:(name) => {
                if(!name){
                    return false;
                }else{
                    return true
                }
            }
        },
        data() {
            return {
                name: '',
            }
        },
    }
</script>

<style scoped>

</style>