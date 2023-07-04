<template>
    <h2>CompositionAPI - {{ firstName }} {{ lastName }}</h2>
    <h2>OptionAPI - {{ fname }} {{ lname }}</h2>
</template>

<script>
    import { reactive, toRefs } from 'vue';

    export default {
        name: 'DemoTwo',
        setup() {
            const state = reactive({
                firstName: 'David',
                lastName: 'Kham',
            })

            setTimeout(() => {
                state.firstName = 'Thurai'
                state.lastName = 'Tun'
            }, 2000)

            return toRefs(state)
        },

        data() {
            return {
                fname: 'Thurai',
                lname: 'Tun',
            }
        }
    }
</script>

<style scoped>

</style>