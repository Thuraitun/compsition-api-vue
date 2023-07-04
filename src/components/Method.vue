<template>
    <h2>{{ name }}</h2>
    <button @click="setName">Change Name</button>
    <h2>{{ count }}</h2>
    <button @click="incrementCount">Increment Count</button>
    
    <h2>{{ firstName }} {{ lastName }}</h2>
    <button @click="heroName">Change Hero Name</button>
</template>

<script>
    import { ref, reactive, toRefs } from 'vue'

    export default {
        name: 'Method',

        setup() {
            const count = ref(0)
            const state = reactive({
                firstName: 'Sai Kham',
                lastName: 'Rai',
            })
            const incrementCount = () => {
                count.value++
            }
            const heroName = () => {
                state.firstName = 'Spider'
                state.lastName = 'Man'
            }

            return {
                count,
                incrementCount,
                ...toRefs(state),
                heroName,
            }
        },

        data() {
            return {
                name: 'Thuraitun',
            }
        },
        methods: {
            setName() {
                this.name = 'David Kham'
            }
        }
    }
</script>

<style scoped>

</style>