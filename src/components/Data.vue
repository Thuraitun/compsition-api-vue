<template>
    <h2>Options - {{ o_firstName }}</h2>
    <h2>Options - {{ o_firstName }} {{ o_lastName }} and {{ o_heroName }}</h2>
    <h2>Composition - {{ c_firstName }}</h2>
    <h2>Composition - {{ greet }}</h2>

    <h2>Composition - {{ c_firstName }} {{ c_lastName }} and {{ c_heroName }}</h2>
    <h2>Composition - {{ greetHero  }}</h2>

    <h2>Composition - {{ state.firstName }} {{ state.lastName }} and {{ state.heroName }}</h2>
    <h2>Composition - {{ reactiveGreetHero }}</h2>
</template>

<script>
    import { ref, reactive } from 'vue'
    export default {
        name: 'Data',
        setup() {
            const c_firstName = ref('David');
            const c_lastName = ref('Kham');
            const c_heroName = ref('Superman');
            console.log('c_firstName', c_firstName)
            const greet = `Hello ${c_firstName.value}`
            const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} and ${c_heroName.value}`

            const state = reactive ({
                firstName: 'Princess',
                lastName:'Diana',
                heroName: 'Wonder Woman',
            })
            const reactiveGreetHero = `Hello ${state.firstName} ${state.lastName} and ${state.heroName}`
 
            // const isLogedIn = ref(false)
            // const isLogedInReactive = reactive({
            //     value: false,
            // })
            return {
                c_firstName,
                c_lastName,
                c_heroName,
                greet,
                greetHero,
                state,
                reactiveGreetHero,
            }
        },
        data() {
            return {
                o_firstName: 'Thurai',
                o_lastName: 'Tun',
                o_heroName: 'Batman',
            }
        }
    }
</script>

<style scoped>

</style>