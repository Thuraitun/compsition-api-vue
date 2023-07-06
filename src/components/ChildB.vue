<template>
    <h4>Child Component B</h4>
    <ChildC />
</template>

<script>
    import ChildC from './ChildC.vue';
    export default {
        name: 'ChildB',
        components: {
            ChildC,
        },
    }
</script>

<style scoped>

</style>