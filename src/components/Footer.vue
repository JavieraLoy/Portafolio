<template>
  <footer class="main-footer">
    <div class="container text-center main-footer__container">
      <div class="main-footer__brand mb-3">
        <span class="main-footer__logo">
          { <span class="main-footer__logo-name">Javiera Loyola</span> }
        </span>
      </div>
      <p class="main-footer__description mb-3">
        Creando experiencias digitales con Vue.js y diseño moderno.
      </p>
      <div class="main-footer__social d-flex justify-content-center gap-4 mb-3">
        <a href="https://github.com/JavieraLoy" target="_blank" class="main-footer__social-link">
          <i class="bi bi-github"></i>
        </a>
        <a href="https://www.linkedin.com/in/javiera-loyola-morales-a85906298/" target="_blank" class="main-footer__social-link">
          <i class="bi bi-linkedin"></i>
        </a>
      </div>
      <small class="main-footer__copyright">
        © {{ year}} Javiera Loyola. Todos los derechos reservados.
      </small>
    </div>
  </footer>
</template>

<script setup>
const year= new Date().getFullYear();
</script>

<style scoped>
.main-footer {
  background-color: #050505;
  position: relative;
  padding: 40px 0;
}

.main-footer::before {
  content: "";
  position: absolute;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 60%;
  height: 2px;
  background: linear-gradient(
    90deg,
    transparent,
    #a855f7,
    #c084fc,
    #a855f7,
    transparent
  );
  box-shadow: 0 0 10px #a855f7, 0 0 20px rgba(168, 85, 247, 0.5);
  animation: glowLine 3s ease-in-out infinite;
}

.main-footer__logo {
  color: #a855f7;
  font-weight: bold;
  font-size: 1.2rem;
}

.main-footer__logo-name {
  color: #fff;
}

.main-footer__description {
  color: #a1a1aa;
}

.main-footer__social-link {
  color: #888;
  font-size: 1.2rem;
  transition: all 0.3s ease;
}

.main-footer__social-link:hover {
  color: #a855f7;
  transform: translateY(-3px);
}

.main-footer__copyright {
  color: #cbd5f5;
  font-size: 0.85rem;
  transition: color 0.3s ease;
}

.main-footer__copyright:hover {
  color: #a855f7;
}

@keyframes glowLine {
  0% {
    opacity: 0.6;
    transform: translateX(-50%) scaleX(0.9);
  }
  50% {
    opacity: 1;
    transform: translateX(-50%) scaleX(1.05);
  }
  100% {
    opacity: 0.6;
    transform: translateX(-50%) scaleX(0.9);
  }
}
</style>