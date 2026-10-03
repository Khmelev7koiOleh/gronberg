<script setup lang="ts">
import { ref } from "vue";
const isMenuOpen = ref(false);
const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>
<template>
  <div class="header">
    <div class="header__body">
      <a href="/" class="header__logo">Jacob Grönberg</a>
      <button
        class="header__menu-button"
        :class="{ 'header__menu-button--open': isMenuOpen }"
        @click="toggleMenu"
        aria-label="Menu"
      >
        <span class="header__menu-button-line"></span>
        <small class=""></small>
      </button>
    </div>
    <nav class="header__menu menu" :class="{ 'menu--open': isMenuOpen }">
      <ul class="menu__list">
        <li class="menu__list-item">
          <a href="/">Home</a>
        </li>
        <li class="menu__list-item">
          <a href="/projects">Projects</a>
        </li>
        <li class="menu__list-item">
          <a href="/exhibitions">Exhibitions</a>
        </li>
        <li class="menu__list-item">
          <a href="/about">About</a>
        </li>
        <li class="menu__list-item">
          <a href="/contact">Contact</a>
        </li>
      </ul>

      <div><Socials /></div>
    </nav>
  </div>
</template>

<style scoped></style>
