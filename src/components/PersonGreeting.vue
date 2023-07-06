<template>
    <h4>Hello {{ fullName }}</h4>
    <button @click="sendEvent">Call Hero</button>
</template>

<script>
    import { computed } from 'vue';

    export default {
        name: 'PersonGreeting',
        setup(props, context) {
            const fullName = computed(() => {
                return `${props.firstName} ${props.lastName}`
            })
            
            const sendEvent = () => {
                context.emit('callHeroes', fullName.value)
            }
            return {
                fullName,
                sendEvent,
            }
        },
        props: ['firstName', 'lastName'],
        emits: ['callHeroes'],
    }
</script>

<style scoped> 

</style>