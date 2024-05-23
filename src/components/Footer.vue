<template>
    <footer>
        <nav>
            <ul>
                <li><router-link to="/">Home</router-link></li>
                <li><router-link to="/projects">Projects</router-link></li>
                <li><router-link to="/about">About Me</router-link></li>
                <li><router-link to="/contact">Contact</router-link></li>
            </ul>
        </nav>
    </footer>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'Footer'
});
</script>

<style scoped>
footer nav ul {
    list-style: none;
    display: flex;
    justify-content: space-around;
}

footer nav ul li {
    padding: 10px;
}
</style>