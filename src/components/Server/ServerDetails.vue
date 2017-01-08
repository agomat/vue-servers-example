<template>
    <div class="col-xs-12 col-sm-6">
        <template v-if="server">
            <p>The server with id {{server.id}} has status: {{server.status}}</p>
            <hr>
            <button @click="toNormal">Set to normal</button>
        </template>
        <template v-else>
            <p>Please click on a server item</p>
        </template>
    </div>

</template>

<script>
    import { eventBus } from '../../main';

    export default {
        data: function () {
            return {
                server: null
            }
        },
        methods: {
            toNormal() {
                this.server.status = 'Normal';
                //eventBus.toNormal(this.server);
            }
        },
        created() {
            eventBus.$on('showDetails', (server) => {
                this.server = server;
            });
        }
    }
</script>

<style>

</style>
