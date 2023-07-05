<template>
    <input type="text" placeholder="first name" v-model="refFirstName">
    <input type="text" placeholder="last name" v-model="refLastName">
    <h4>Composition API Computed FullName - {{ refFullname }}</h4>

    <input type="text" placeholder="first name" v-model="reactiveFirstName">
    <input type="text" placeholder="last name" v-model="reactiveLastName">
    <h4>Reactive FullName - {{ reactiveFullName }}</h4>
</template>

<script>
    import { ref ,computed, reactive, toRefs } from 'vue';

    export default {
        name: 'Computed',
        setup() {
            const refFirstName = ref('')
            const refLastName = ref('')
            const refFullname = computed(() => {
                return `${refFirstName.value} ${refLastName.value}`
            })

            const state = reactive({
                reactiveFirstName: '',
                reactiveLastName: '',
            })

            const reactiveFullName = computed(() => {
                return `${state.reactiveFirstName} ${state.reactiveLastName}`
            })
            
            return {
                refFirstName,
                refLastName,
                refFullname,
                ...toRefs(state),
                reactiveFullName
            }
        }  
    }
</script>

<style scoped>

</style>