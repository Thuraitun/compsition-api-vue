<template>
    <h4>Child Component A</h4>
    <ChildB />
</template>

<script>
    import ChildB from './ChildB.vue';
    export default {
        name: 'ChildA',
        components: {
            ChildB,
        },

    }
</script>

<style scoped>

</style>