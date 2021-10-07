<template>
    <div>

    </div>
</template>

<script>
import {onBeforeMount,
        onMounted,
        onBeforeUpdate,
        onUpdated,
        onBeforeUnmount,
        onUnmounted,
} from 'vue'
    export default {
        name: 'replaceLifeCycleC',
        setup() {
            onBeforeMount(() =>{
            console.log('LifeCycleC onBeforeMount()')
            })
            onMounted(() => {
            console.log('LifeCycleC Mounted()')
            })
            onBeforeUpdate(() => {
            console.log('LifeCycleC onBeforeUpdate()')
            })
            onUpdated(() => {
            console.log('LifeCycleC onUpdated()')  
            })
            onBeforeUnmount(() => {
            console.log('LifeCycleC onBeforeUnMount()')
            })
            onUnmounted(() => {
            console.log('LifeCycleC onUnmounted()')
            })
        }
    }
</script>

<style scoped>

</style>