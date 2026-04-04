<template>
  <section class="projects">
    <div class="container">
      <div class="projects__header text-center">
        <h1 class="projects__title">
          Mis 
          <span class="text-neon">
            {{ typedTitle }}<span class="cursor">|</span>
          </span>
        </h1>
        <p class="projects__subtitle">
          Algunos de los proyectos donde he aplicado Vue, consumo de APIs y diseño moderno.
        </p>
      </div>
      <div class="row g-4">
        <div 
          class="col-12 col-md-6 col-lg-4 d-flex"
          v-for="project in projects"
          :key="project.id"
        >
          <ProjectCard
            :title="project.title"
            :description="project.description"
            :image="project.image"
            :repo="project.repo"
            :demo="project.demo"
            :tags="project.tags"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import ProjectCard from '../components/ProjectCard.vue';
import projectsData from '../data/projects.json';
import { ref, onMounted } from 'vue'

const base= import.meta.env.BASE_URL;
const projects= projectsData.map(project => ({
  ...project,
  image: base + project.image
}));

const fullText = '{ Proyectos }'
const typedTitle = ref('')
let index = 0

onMounted(() => {
  const typing = setInterval(() => {
    if (index < fullText.length) {
      typedTitle.value += fullText[index]
      index++
    } else {
      clearInterval(typing)
    }
  }, 150)
});
</script>

<style scoped>
.projects {
  padding: 120px 0 80px;
  background: radial-gradient(circle at 50% 0%, rgba(168, 85, 247, 0.08), transparent 60%);
}

.projects__header {
  margin-bottom: 60px;
}

.projects__title {
  color: #fff;
  font-size: 2.5rem;
  font-weight: 700;
}

.projects__subtitle {
  color: #a1a1aa;
  max-width: 600px;
  margin: 0 auto;
}

.text-neon {
  color: #c084fc;
  text-shadow: 0 0 20px rgba(168, 85, 247, 0.7);
}

.cursor {
  display: inline-block;
  margin-left: 2px;
  animation: blink 1s infinite;
}

@keyframes blink {
  0%, 50%, 100% { opacity: 1; }
  25%, 75% { opacity: 0; }
}

.projects .row > div {
  animation: fadeUp 0.6s ease forwards;
  opacity: 0;
}

.projects .row > div:nth-child(1) { 
  animation-delay: 0.1s; 
}
.projects .row > div:nth-child(2) {
  animation-delay: 0.2s; 
}
.projects .row > div:nth-child(3) { 
  animation-delay: 0.3s; 
}

@keyframes fadeUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>