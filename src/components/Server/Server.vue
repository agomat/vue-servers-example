<template>
    <li
            class="list-group-item"
            style="cursor: pointer"
            @click="showDetails(server)">
        Server #{{ server.id }}
    </li>
</template>

<script>
    import { eventBus } from '../../main';

    export default {
        props: ['server'],
        methods: {
            showDetails( server ) {
                eventBus.$emit('showDetails', server)
            }
        }

    }
</script>

<style>

</style>
