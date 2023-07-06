<template>
    <h4>Child Component C</h4>
    <h5><i>Child Component C Username - {{ userName }}</i></h5>
    <h5><i>Child Component C composition Username - {{ childUserName }}</i></h5>
    <h5><i>Child Component C composition Count - {{ childCount }}</i></h5>
    <button @click="childIncrement">Increment Count from Child</button>
    <h5><i>Child Component C composition Hero - {{ firstName }} {{ lastName }}</i></h5>
</template>

<script>
    import { inject, toRefs } from 'vue';
    export default {
        name: 'ChildC',
        setup() {
            const childUserName = inject('c_userName', 'Default UserName')
            const childCount = inject('c_count', 0)
            const childHero = inject('c_hero', {})
            const childIncrement = inject('incrementCount')

            return {
                childUserName,
                childCount,
                ...toRefs(childHero),
                childIncrement,
            }
        },
        inject: ['userName']
    }
</script>

<style scoped>
    h5 {
        color: blue;
    }
</style>