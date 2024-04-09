<script setup>
import { RouterLink } from 'vue-router'

</script>

<template>
 <nav class="navbar navbar-expand-lg bg-white navbar-light shadow-sm py-3 py-lg-0 px-3 px-lg-0">
        <RouterLink to="/"><a href="" class="navbar-brand ms-lg-5">
            <h1 class="m-0 text-uppercase text-dark"><i class="bi bi-droplet-half fs-1 text-primary me-3"></i>BOTW MONSTERs</h1>
        </a></RouterLink>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarCollapse">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarCollapse">
            <div class="navbar-nav ms-auto py-0 mx-4">
                <RouterLink to="/"><a href="index.html" class="nav-item nav-link">Home</a></RouterLink>
                <RouterLink to="/monsters"><a href="" class="nav-item nav-link">Monsters</a></RouterLink>          
            </div>
        </div>
    </nav>

</template>

<style scoped>
.router-link-active{
       
    }
</style>