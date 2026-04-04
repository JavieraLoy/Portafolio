<script setup>
import Navbar from './components/Navbar.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <div id="app">
    <Navbar/>
    <main class="pt-5">
      <router-view v-slot="{Component}">
        <Transition name="fade" mode="out-in">
          <component :is="Component"/>
        </Transition>
      </router-view>
    </main>
    <Footer></Footer>
  </div>
</template>

<style>
body, html{
  margin: 0;
  padding: 0;
  font-family: 'Inter', sans-serif;
  background-color: #0b0b0b;
  color: #333;
}
#app{
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
main{
  flex: 1;
}
.fade-enter-active, .fade-leave-active{
  transition: opacity 0.4s ease;
}
.fade-enter-form, .fade-leave-to{
  opacity: 0;
}

</style>

