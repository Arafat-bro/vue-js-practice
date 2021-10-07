<template>
    <div v-show="false">
        <h2 @mouseover="increament">Hovered {{count}} times</h2>
    </div>
</template>

<script>
import CounterMixin from '../Mixins/Counter'
    export default {
        name:'HoverCounter',
        mixins : [CounterMixin]
    }
</script>

<style scoped>

</style>