<template>
    <section class="projects-section">
        <h1 class="projects-title">projects</h1>
        <div class="projects-grid">
            <div class="project-card" v-for="project in projects" :key="project.id">
                <img :src="project.image" :alt="project.title" class="project-image" />
                <h2 class="project-title">{{ project.title }}</h2>
                <p class="project-description">{{ project.description }}</p>
                <a :href="project.link" target="_blank" class="project-link">View Project</a>
            </div>
        </div>
    </section>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
    name: 'Projects',
    setup() {
        const projects = ref([
            {
                id: 1,
                title: 'Project One',
                description: 'This is a brief description of project one.',
                image: 'path/to/image1.jpg',
                link: 'https://example.com/project1'
            },
            {
                id: 2,
                title: 'Project Two',
                description: 'This is a brief description of project two.',
                image: 'path/to/image2.jpg',
                link: 'https://example.com/project2'
            },
            {
                id: 3,
                title: 'Project Three',
                description: 'This is a brief description of project three.',
                image: 'path/to/image3.jpg',
                link: 'https://example.com/project3'
            },
            {
                id: 4,
                title: 'Project Four',
                description: 'This is a brief description of project four.',
                image: 'path/to/image4.jpg',
                link: 'https://example.com/project4'
            },
            {
                id: 5,
                title: 'Project Five',
                description: 'This is a brief description of project five.',
                image: 'path/to/image5.jpg',
                link: 'https://example.com/project5'
            },
            {
                id: 6,
                title: 'Project Six',
                description: 'This is a brief description of project six.',
                image: 'path/to/image6.jpg',
                link: 'https://example.com/project6'
            }
        ]);

        return { projects };
    }
});
</script>

<style lang="scss" scoped>
.projects-section {
    padding: 50px;
    background-color: var(--bg-color);
    color: var(--text-color);

    .projects-title {
        text-align: center;
        font-size: 2.5rem;
        margin: 40px;
    }

    .projects-grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 70px;

        .project-card {
            background-color: var(--card-bg-color);
            color: var(--text-color);
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: background-color 0.3s, color 0.3s;

            .project-image {
                max-width: 100%;
                height: auto;
                border-radius: 4px;
                margin-bottom: 20px;
            }

            .project-title {
                font-size: 1.5rem;
                margin-bottom: 10px;
            }

            .project-description {
                font-size: 1rem;
                margin-bottom: 20px;
            }

            .project-link {
                display: inline-block;
                padding: 10px 20px;
                background-color: var(--button-bg-color);
                color: var(--button-text-color);
                text-decoration: none;
                border-radius: 5px;
                transition: background-color 0.3s, color 0.3s;

                &:hover {
                    background-color: var(--button-hover-bg-color);
                    color: var(--button-hover-text-color);
                }
            }
        }
    }
}
</style>