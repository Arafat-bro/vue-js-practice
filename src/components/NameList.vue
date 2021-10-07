<template >
    <div v-show="false">
        <!-- <h3 v-for="name in names" :key="name.firstName">
            {{name.firstName}} {{name.lastName}}
        </h3> -->
         <h3 v-for="name in names" :key="name.firstName">
             <slot :fName="name.firstName" :lName="name.lastName"></slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name:'NameList',
        data() {
            return {
                names:[{
                    firstName : 'Bruce',
                    lastName : 'Lee'
                },
                {
                    firstName : 'Clark',
                    lastName : 'Kent'
                },{
                    firstName : 'Wonder',
                    lastName : 'Man'
                },{
                    firstName : '3ree',
                    lastName : 'Pie'
                }],
            }
        },
    }
</script>

<style scoped>

</style>