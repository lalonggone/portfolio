<template>
    <section class="projects-section">
        <h1 class="projects-title">My Projects</h1>
        <div class="projects-grid">
            <div class="project-card" v-for="project in projects" :key="project.id">
                <h2 class="project-title">{{ project.title }}</h2>
                <p class="project-description">{{ project.description }}</p>
                <a v-if="project.link" :href="project.link" target="_blank" class="project-link">View Project</a>
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
                title: 'Kane Creek Comments',
                description: 'A full-stack web app that allows users to filter, search and display thousands of survey responses regarding a development in Utah.',
                link: 'https://kane-creek-comments.vercel.app/'
            },
            {
                id: 2,
                title: 'Travel Tracker',
                description: 'A dynamic web app that allows users to manage trips. With a clean UI, travelers can view their upcoming trips, pending trips, estimate travel costs and book new trips.',
                link: 'https://github.com/lalonggone/travel-tracker'
            },
            {
                id: 3,
                title: 'Moab Bike Hub',
                description: 'Coming soon - stay tuned!',
            },
            {
                id: 4,
                title: 'Rock Paper Scissors',
                description: 'A game featuring two modes - classic and EXTREME! Set up to be played against a computer that generates random choices against the user. ',
                link: 'https://lalonggone.github.io/rockPaperScissors/'
            },
            {
                id: 5,
                title: 'Kane Creek Survey Petition',
                description: 'A handrolled a petition form serving as a petition against the proposed development in the Colorado River corridor near Moab, Utah.',
                link: 'https://lalonggone.github.io/kc-comp/index.html'
            },
            {
                id: 6,
                title: 'Blank',
                description: 'Coming soon - stay tuned!'

            }
        ]);

        return { projects };
    }
});
</script>

<style lang="scss" scoped>
@import '../_variables.scss';

.projects-section {
    padding: 50px;
    background-color: var(--bg-color);
    color: var(--text-color);

    .projects-title {
        text-align: center;
        font-size: 2.5rem;
        margin: 40px 0 30px;
    }

    .projects-grid {
        display: grid;
        grid-template-columns: 1fr;
        gap: 4vh;

        @media (min-width: $screen-sm) {
            grid-template-columns: repeat(1, 1fr);
            // margin-top: 50px;
        }
        @media (min-width: $screen-md) {
            grid-template-columns: repeat(2, 1fr);
        }

        @media (min-width: $screen-lg) {
            grid-template-columns: repeat(3, 1fr);
        }
        
        .project-card {
            background-color: var(--card-bg-color);
            color: var(--text-color);
            padding: 25px;
            border-radius: 8px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
            text-align: center;
            transition: background-color 0.3s, color 0.3s;
            min-width: 250px;
            max-width: 400px;
            
            .project-title {
                font-size: 1.5rem;
                margin-bottom: 10px;
            }

            .project-description {
                font-size: 0.9rem;
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