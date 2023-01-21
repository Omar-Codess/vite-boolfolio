<script>
import axios from 'axios';

export default {
    name: "AppMain",
    data() {
    return {
      projects: []
    }
  },
  created() {
    this.getProjects();
  },
  methods: {
    getProjects() {
      axios.get('http://127.0.0.1:8000/api/projects').then(resp => {
        this.projects = resp.data.results;
      })
    }
  }
}
</script>

<template>
    <div class="container">
        <h2>Main section</h2>
    </div>
</template>

<style>

</style>