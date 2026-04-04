<template>
  <section class="about d-flex container py-5">
    <div class="row align-items-center">
      <div class="col-md-6 mb-4">
        <div class="about__card text-center position-relative p-4">
          <div class="about__photo-container">
            <img :src="base + 'img/fotoperfil.jpg'" alt="foto perfil" class="about__photo">
          </div>
          <div class="about__content mt-5">
            <h2 class="about__title mb-3">Sobre mí</h2>
            <p class="about__text">
              Soy desarrolladora frontend en formación, enfocada en la creación de aplicaciones web modernas con Vue.js.
              He trabajado en proyectos que incluyen consumo de APIs REST, manejo de rutas con Vue Router y gestión de estado con Vuex, desarrollando interfaces dinámicas y responsivas.
            </p>
            <p class="about__text">
              Cuento con formación en desarrollo frontend y experiencia utilizando tecnologías como JavaScript, HTML, CSS, Vue 3, Axios y Git. 
              Me interesa construir interfaces intuitivas y seguir creciendo en el ecosistema frontend, enfrentando nuevos desafíos y mejorando continuamente mis habilidades.
            </p>     
          </div>
        </div>
       </div>
       <div class="col-md-6 text-center">
         <div class="about__tech mb-4">
           <h3 class="about__subtitle mb-3">Tecnologías</h3>
           <span class="badge about__badge">HTML5</span>
           <span class="badge about__badge">CSS3</span>
           <span class="badge about__badge">JavaScript</span>
           <span class="badge about__badge">Vue 3</span>
           <span class="badge about__badge">Vue router</span>
           <span class="badge about__badge">Vuex</span>
           <span class="badge about__badge">Axios</span>
           <span class="badge about__badge">Git</span>
           <span class="badge about__badge">GitHub</span>
         </div>
         <div class="about__contact">
           <h3 class="about__subtitle">Contáctame</h3>
           <a href="https://mail.google.com/mail/?view=cm&to=javiera.loyola.morales@gmail.com" target="_blank" class="btn about__btn me-2">
             Enviar correo
           </a>
           <a :href="base + 'JavieraLoyolaCV.pdf'" download class="btn about__btn">
             Descargar CV
           </a>
         </div>
       </div>
    </div>
  </section>
</template>
<script setup>
const base= import.meta.env.BASE_URL;

</script>
<style scoped>
.about {
  color: #fff;
  padding-top: 80px;
  padding-bottom: 40px;
  min-height: 100vh;
}

.about__card {
  background: rgba(20, 20, 40, 0.8);
  border-radius: 20px;
  border: 1px solid #a855f7;
  box-shadow: 0 0 20px #a855f7;
}

.about__photo-container {
  position: absolute;
  top: -50px;
  left: 5%;
  transform: translateX(-40%);
}

.about__photo {
  width: 140px;
  height: 140px;
  border-radius: 50%;
  border: 3px solid #a855f7;
  box-shadow: 0 0 15px #a855f7;
  object-fit: cover;
}

.about__title {
  color: #c084fc;
}

.about__subtitle {
  color: #c084fc;
  font-weight: 600;
  font-size: 2.5rem;
}

.about__text {
  font-size: 0.95rem;
  line-height: 1.5;
}

.about__badge {
  background: transparent;
  border: 1px solid #a855f7;
  color: #fff;
  margin: 5px;
  box-shadow: 0 0 10px #a855f7;
  font-size: 1rem;
  padding: 12px 20px;
  border-radius: 20px;
}

.about__btn {
  background: transparent;
  border: 1px solid #a855f7;
  color: #fff;
  box-shadow: 0 0 10px #a855f7;
  transition: 0.3s;
}

.about__btn:hover {
  background: #a855f7;
  color: #000;
}
</style>