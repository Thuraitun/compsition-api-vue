<template>
    <!-- Options API -->
    <input type="text" placeholder="Enter Your Name" v-model="watchName">

    <input type="text" placeholder="First Name" v-model="firstName">
    <input type="text" placeholder="Last Name" v-model="lastName">

    <input type="text" placeholder="Reactive First Name" v-model="fName">
    <input type="text" placeholder="Reactive Last Name" v-model="lName">
    <input type="text" placeholder="Reactive Hero Name" v-model="option.heroName">
</template>

<script>
    import {ref, watch, reactive, toRefs} from 'vue'
    import _ from 'lodash'
    export default {
        name: 'Watch',
        setup() {
            const state = reactive({
                fName: '',
                lName: '',
                option: {
                    heroName: '',
                }
            })
            
            // watch(() => {
            //     return {...state}
            // },function (newValue, oldValue) {
            //     console.log('fName Old value', oldValue.fName)
            //     console.log('fName Value', newValue.fName)
            //     console.log('lName Old value', oldValue.lName)
            //     console.log('lName New Value', newValue.lName)
            // })

            watch(() => _.cloneDeep(state.option), function(newValue, oldValue) {
                console.log('Hero Old value', oldValue)
                console.log('Hero New value', newValue)
            }, {
                deep: true,
            })

            const firstName = ref('')
            const lastName = ref('Rai')

            watch([firstName, lastName], (newValues, oldValues) => {
                console.log('firstName Old value', oldValues[0])
                console.log('firstName New Value', newValues[0])
                console.log('lastName Old value', oldValues[1])
                console.log('lastName New Value', newValues[1])
            }, {
                immediate: true,
            })

            return {
                firstName,
                lastName,
                ...toRefs(state),
            }
        },
        data() {
            return {
                watchName: ''
            }
        },
        watch: {
            watchName(newValue, oldValue) {
                console.log('Old value', oldValue)
                console.log('New Value', newValue)
            }
        }
    }
</script>

<style scoped>

</style>