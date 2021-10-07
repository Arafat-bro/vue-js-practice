<template>
    <div>
        <replace-methods></replace-methods>
        <v-modelc-a-p-i></v-modelc-a-p-i>
        <replace-computed></replace-computed>
        <replace-watchers></replace-watchers>
        <replaceProvideInject></replaceProvideInject>
        <templateRefComAPI></templateRefComAPI>
        <person></person>
        <ReUseApiClickCounter></ReUseApiClickCounter>
        <ReUseApiHoverCounter/>
    </div>
</template>

<script>
import replaceMethods from '@/components/replaceMethods'
import vModelcAPI from '@/components/vModelcAPI'
import replaceComputed from '@/components/replaceComputed'
import replaceWatchers from '@/components/replaceWatchers'
import replaceProvideInject from '@/components/replaceProvideInject'
import templateRefComAPI from '@/components/templateRefComAPI'
import Person from '@/components/Person'
import ReUseApiClickCounter from '@/components/ReUseApiClickCounter'
import ReUseApiHoverCounter from '@/components/ReUseApiHoverCounter'
    export default {
        name: 'App9',
        components : {
            replaceMethods,
            vModelcAPI,
            replaceComputed,
            replaceWatchers,
            replaceProvideInject,
            templateRefComAPI,
            Person,
            ReUseApiClickCounter,
            ReUseApiHoverCounter

        }
    }
</script>

<style scoped>

</style>