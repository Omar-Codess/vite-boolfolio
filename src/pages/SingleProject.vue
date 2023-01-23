<script>
import axios from 'axios';
import {store} from "../store";

export default {
    name: "SingleProject",
    data() {
        return {
            store
        }
    },
    created() {
        axios.get(``)
    }
}
</script>

<template>
    <div class="container mt-3">
        <h1 class="mt-3 text-center">Single Project</h1>
    </div>
</template>