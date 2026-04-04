<template>
  <div class="project-card">
    <div class="project-card__image-wrapper">
      <img :src="image" :alt="title" class="project-card__image" />
      <div class="project-card__overlay">
        <a :href="demo" target="_blank" class="project-card__btn project-card__btn--primary">Ver Demo</a>
        <a :href="repo" target="_blank" class="project-card__btn project-card__btn--secondary">Código</a>
      </div>
    </div>
    <div class="project-card__content">
      <div class="project-card__tags">
        <span v-for="tag in tags" :key="tag" class="project-card__tag">
          {{ tag }}
        </span>
      </div>
      <h3 class="project-card__title">{{ title }}</h3>
      <p class="project-card__description">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  image: String,
  repo: String,
  demo: String,
  tags: Array
})

</script>

<style scoped>
.project-card {
  display: flex;
  flex-direction: column;
  width: 100%;
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(168, 85, 247, 0.15);
  border-radius: 16px;
  overflow: hidden;
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}

.project-card:hover {
  transform: translateY(-6px);
  box-shadow: 0 10px 30px rgba(168, 85, 247, 0.2);
}

.project-card__image-wrapper {
  position: relative;
  overflow: hidden;
}

.project-card__image {
  width: 100%;
  height: 200px;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.project-card:hover .project-card__image {
  transform: scale(1.05);
}

.project-card__overlay {
  position: absolute;
  inset: 0;
  background: rgba(5, 5, 5, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.project-card:hover .project-card__overlay {
  opacity: 1;
}

.project-card__content {
  padding: 20px;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.project-card__tags {
  margin-bottom: 10px;
}

.project-card__tag {
  font-size: 0.75rem;
  padding: 4px 10px;
  margin-right: 6px;
  border-radius: 20px;
  background: rgba(168, 85, 247, 0.1);
  color: #c084fc;
  border: 1px solid rgba(168, 85, 247, 0.2);
}

.project-card__title {
  color: #fff;
  font-size: 1.2rem;
  margin-bottom: 10px;
}

.project-card__description {
  color: #a1a1aa;
  font-size: 0.9rem;
  line-height: 1.4;
  flex-grow: 1;
}

.project-card__btn {
  padding: 6px 14px;
  border-radius: 6px;
  font-size: 0.85rem;
  text-decoration: none;
  transition: all 0.3s ease;
}

.project-card__btn--primary {
  background-color: #a855f7;
  color: white;
}

.project-card__btn--primary:hover {
  background-color: #9333ea;
  box-shadow: 0 0 10px #a855f7;
}

.project-card__btn--secondary {
  border: 1px solid #ccc;
  color: #ddd;
}

.project-card__btn--secondary:hover {
  border-color: #a855f7;
  color: #a855f7;
}
</style>