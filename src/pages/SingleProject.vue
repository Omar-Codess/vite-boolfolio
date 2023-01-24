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
                this.$router.push({name: "not-found"});
            }
        });
    },
    computed: {
        category() {
            return this.project.category ? this.project.category.name :  'Nessuna categoria';
        }
    }
}
</script>

<template>
    <div class="container mt-3">
        <h1 class="mt-3 text-center">{{ project.title }}</h1>
        <h5 class="text-center mt-3 text-uppercase text-primary">{{ category }}</h5>
        <img v-if="project.cover_image" :src="`${store.apiBaseUrl}/storage/${project.cover_image}`" alt="">
        <div v-else class="text-center mt-2">Nessuna immagine trovata</div>
        <p>{{ project.description }}</p>
    </div>
</template>