<template>
    <h4>Parent Component {{ name }} </h4>
    <h4>Parent Component Count {{ count }} </h4>
    <button @click="incrementCount">Increment Count</button>
    <h4>Parent Component Hero {{ firstName }} {{ lastName }} </h4>
    <ChildA />
</template>

<script>
    import { provide, ref, reactive, toRefs } from 'vue';
    import ChildA from './ChildA.vue';
    export default {
        name: 'ProvideInject',
        components: {
            ChildA,
        },
        setup() {
            provide('c_userName', 'Vue Learner')

            const count = ref(0)
            const incrementCount = () => {
                count.value ++
            }
            const state = reactive({
                firstName: 'Thurai',
                lastName: 'Tun',
            })

            provide('c_count', count)
            provide('c_hero', state)
            provide('incrementCount', incrementCount)

            return {
                count,
                ...toRefs(state),
                incrementCount
            }
        },
        data() {
            return {
                name: 'Shwe Mi',
            }
        },
        provide() {
            return {
                userName: this.name,
            }
        }
    }
</script>

<style scoped>

</style>