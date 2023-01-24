<script>
import axios from 'axios';
import {store} from "../store";

export default {
    name: "SingleProject",
    data() {
        return {
            store,
            project: {}
        }
    },
    created() {
        const slug = this.$route.params.slug;
        axios.get(`${this.store.apiBaseUrl}/api/projects/${slug}`).then(resp => {
            if(resp.data.success) {
                this.project = resp.data.project;
            } else {
                this.$router.push({name: "not-found"})
            }
        });
    }
}
</script>

<template>
    <div class="container mt-3">
        <h1 class="mt-3 text-center">Single Project</h1>
    </div>
</template>