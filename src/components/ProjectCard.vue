<script>
export default {
    name: 'ProjectCard',
    data() {
        return {
            descriptionMaxLength: 200
        }
    },
    props: {
        project: Object
    },
    methods: {
        truncateText(text) {
            if (text && text.length > this.descriptionMaxLength) {
                return text.substr(0, this.descriptionMaxLength) + '...'
            } 
            return text;
        }
    }
}
</script>

<template>
    <div class="card mb-3">
        <div class="card-body">
            <h3 class="card-title">{{ project.title }}</h3>
            <p class="card-text">
                {{ truncateText(project.description) }}
            </p>
            <router-link :to="{name: 'single-project', params: {slug: project.slug}}" class="btn btn-primary" href="">Leggi</router-link>
        </div>
    </div>
</template>

<style>

</style>