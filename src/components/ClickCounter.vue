<template>
    <div v-show="false">
        <button @click="increament">Clicked {{count}} times</button>
    </div>
</template>

<script>
import CounterMixin from '../Mixins/Counter'
    export default {
        name:'ClickCounter',
        mixins : [CounterMixin]
    }
</script>

<style scoped>

</style>