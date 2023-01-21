<script>
import axios from 'axios';

export default {
    name: "AppMain",
    data() {
    return {
        baseUrl: 'http://127.0.0.1:8000',
        projects: []
    }
  },
  created() {
    this.getProjects();
  },
  methods: {
    getProjects() {
      axios.get(`${this.baseUrl}/api/projects`).then(resp => {
        this.projects = resp.data.results;
      })
    }
  }
}
</script>

<template>
    <div class="container">
        <h2>Tutti i progetti</h2>
        <div class="row justify-content-center">
            <div class="col-11 col-md-10 col-lg-8">
                <div class="card mb-3" v-for="project in projects" :key="project.id">
                    <div class="card-body">
                        <h3 class="card-title">{{ project.title }}</h3>
                        <p class="card-text">{{ project.description }}</p>
                        <a class="btn btn-primary" href="">Leggi</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>

</style>