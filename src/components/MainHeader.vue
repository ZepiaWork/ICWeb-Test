<script setup>
import { ref } from 'vue'
const isScrollDown = ref(false)
window.addEventListener('scroll', function () {
    const scrolled = window.scrollY
    if (scrolled > 100) {
        isScrollDown.value = true
    } else {
        isScrollDown.value = false
    }
})
</script>

<template>
    <nav class="navbar fixed-top navbar-expand-lg" :class="{ shadow: isScrollDown }">
        <div class="container">
            <a class="navbar-brand text-white fs-3" href="#">&#60;/&#62; Developer</a>
            <!-- <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button> -->
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto text-uppercase mb-2 mb-lg-0 text-white">
                    <li class="nav-item">
                        <a class="nav-link" aria-current="page" href="#">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#services">Services</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="#great-work">Great work</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<style scoped>
.navbar-nav {
    --bs-navbar-color: white;
}
.navbar {
    transition: background-color 0.6s;
}
.navbar.shadow {
    background-color: rgba(0, 0, 0, 1);
}
</style>
