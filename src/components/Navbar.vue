<template>
  <nav class="navbar navbar-expand-lg fixed-top main-nav">
    <div class="container main-nav__container">
      <router-link class="navbar-brand main-nav__brand" to="/">
        <span class="main-nav__logo">{ <span class="main-nav__logo-name">Javiera Loyola</span> }</span>
      </router-link>
      <button class="navbar-toggler border-0 main-nav__toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
        <i class="bi bi-list main-nav__icon"></i> 
      </button>

      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav ms-auto align-items-center main-nav__menu">
          <li class="nav-item">
            <router-link class="nav-link main-nav__link" to="/">Inicio</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link main-nav__link" to="/about">Sobre mí</router-link>
          </li>
          <li class="nav-item">
            <router-link class="nav-link main-nav__link" to="/proyectos">Proyectos</router-link>
          </li>
          <li class="nav-item d-none d-lg-block mx-3">
            <div class="vr main-nav__divider"></div>
          </li>
          <li class="nav-item d-flex gap-3 main-nav__social">
            <a href="https://github.com/JavieraLoy" target="_blank" rel="noopener noreferrer" class="main-nav__social-link"><i class="bi bi-github"></i></a>
            <a href="https://www.linkedin.com/in/javiera-loyola-morales-a85906298/" target="_blank" class="main-nav__social-link"><i class="bi bi-linkedin"></i></a>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.main-nav {
  backdrop-filter: blur(8px);
  padding: 1.5rem 0; 
}

.main-nav__container {
  display: flex;
  align-items: center;
}

.main-nav__brand {
  font-weight: bold;
}

.main-nav__logo {
  color: #a855f7;
}

.main-nav__logo-name {
  color: #fff;
}

.main-nav__icon {
  font-size: 2rem;
  color: #a855f7; 
}

.main-nav__link {
  color: #888; 
  font-size: 0.95rem;
  font-weight: 400;
  transition: color 0.3s ease;
}

.main-nav__link:hover, 
.router-link-active {
  color: #ffffff !important;
}

.main-nav__divider {
  height: 20px;
  background-color: rgba(255, 255, 255, 0.2);
}

.main-nav__social-link {
  color: #888;
  font-size: 1.1rem;
  transition: color 0.3s ease;
}

.main-nav__social-link:hover {
  color: #a855f7;
}
</style>