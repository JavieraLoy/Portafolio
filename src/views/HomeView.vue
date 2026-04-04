<template>
  <section class="hero d-flex align-items-center">
    <div class="hero__bg-blur"></div>
    <div class="container hero__container">
      <div class="row justify-content-center text-center">
        <div class="col-lg-9">
          <span class="hero__badge mb-4">
            <span class="hero__dot"></span> Disponible para nuevos proyectos
          </span>
          <h1 class="hero__title mb-4">
            Hola, soy 
            <span class="hero__name">{{typedName}}<span class="hero__cursor">|</span></span>
          </h1>
          <h2 class="hero__subtitle mb-4">
            Frontend Developer Trainee
          </h2>
          <p class="hero__description lead mx-auto mb-5">
            Desarrollo interfaces intuitivas con <span class="hero__highlight">Vue.js</span> y <span class="hero__highlight">CSS moderno</span>. 
            Transformando necesidades de negocio en experiencias digitales memorables.
          </p>
          <div class="hero__actions d-flex justify-content-center gap-3">
            <router-link to="/proyectos" class="hero__btn hero__btn--primary">
              Ver Proyectos
            </router-link>
            <a href="https://mail.google.com/mail/?view=cm&to=javiera.loyola.morales@gmail.com" target="_blank" class="hero__btn hero__btn--secondary">
              Contáctame
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script setup>
import { ref, onMounted } from 'vue'

const fullText = '{ Javiera }'
const typedName = ref('')
let index = 0

onMounted(() => {
  const typing = setInterval(() => {
    if (index < fullText.length) {
      typedName.value += fullText[index]
      index++
    } else {
      clearInterval(typing)
    }
  }, 150)
});
</script>

<style scoped>
.hero {
  min-height: 100vh;
  background-color: #050505; 
  position: relative;
  overflow: hidden;
  display: flex;
  align-items: center;
  background: radial-gradient(circle at 50% 50%, rgba(168, 85, 247, 0.15) 0%, #050505 80%);
}

.hero__bg-blur {
  position: absolute;
  top: 15%;
  right: 10%;
  width: 550px;
  height: 550px;
  background: radial-gradient(circle, rgba(168, 85, 247, 0.15), transparent 70%);
  filter: blur(80px);
  z-index: 0;
}

.hero__container {
  position: relative;
}

.hero__badge {
  display: inline-flex;
  align-items: center;
  padding: 6px 16px;
  background: rgba(168, 85, 247, 0.1);
  border: 1px solid rgba(168, 85, 247, 0.2);
  color: #a855f7;
  border-radius: 50px;
  font-size: 0.9rem;
}

.hero__dot {
  width: 8px;
  height: 8px;
  background-color: #a855f7;
  border-radius: 50%;
  margin-right: 10px;
  box-shadow: 0 0 10px #a855f7;
  animation: pulse 2s infinite;
}

.hero__title {
  font-size: 4rem;
  font-weight: 700;
  color: #fff;
}

.hero__name {
  color: #c084fc; 
  text-shadow: 0 0 30px rgba(168, 85, 247, 0.8);
}
.hero__cursor {
  display: inline-block;
  margin-left: 2px;
  animation: blink 1s infinite;
}

.hero__subtitle {
  color: #e2e8f0;
  font-weight: 300;
}

.hero__description {
  color: #a1a1aa;
  max-width: 600px;
}

.hero__highlight {
  color: #fff;
  font-weight: 600;
}

.hero__btn {
  padding: 8px 20px;
  border-radius: 6px;
  font-size: 0.9rem;
  text-decoration: none;
  transition: all 0.3s ease;
}

.hero__btn--primary {
  background-color: #a855f7;
  color: white;
  border: none;
  box-shadow: 0 4px 15px rgba(168, 85, 247, 0.4);
}

.hero__btn--primary:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(168, 85, 247, 0.6);
  background-color: #9333ea;
}

.hero__btn--secondary {
  border: 1px solid #ccc;
  color: #ddd;
}

.hero__btn--secondary:hover {
  border-color: #a855f7;
  color: #a855f7;
}

@keyframes blink {
  0%, 50%, 100% { opacity: 1; }
  25%, 75% { opacity: 0; }
}

@keyframes pulse {
  0% { transform: scale(0.95); opacity: 0.7; }
  70% { transform: scale(1.1); opacity: 1; }
  100% { transform: scale(0.95); opacity: 0.7; }
}
</style>