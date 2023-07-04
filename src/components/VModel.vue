<template>
    <input type="text" placeholder="Fav Hero" v-model="favName"><br>
    <input type="text" placeholder="First Name" v-model="fName"><br>
    <input type="text" placeholder="Last Name" v-model="lName">
</template>

<script>
    import { ref, reactive, toRefs } from 'vue'
    export default {
        name: 'VModel',
        setup() {
            const favName = ref('')
            const state = reactive({
                fName: '',
                lName: '',
            })

            return {
                favName,
                ...toRefs(state)
            }
        }
    }
</script>

<style scoped>

</style>