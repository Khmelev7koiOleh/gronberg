<template>
  <ul class="socials">
    <li class="socials__item">
      <a
        href="#"
        target="_blank"
        rel="noopener noreferrer"
        class="socials__link"
        >Twitter</a
      >
    </li>
    <li class="socials__item">
      <a
        href="#"
        target="_blank"
        rel="noopener noreferrer"
        class="socials__link"
        >Instagram</a
      >
    </li>
    <li class="socials__item">
      <a
        href="#"
        target="_blank"
        rel="noopener noreferrer"
        class="socials__link"
        >Facebook</a
      >
    </li>
  </ul>
</template>

<script setup lang="ts"></script>

<style scoped lang="scss">
@use "@/assets/scss/style" as *;
.socials {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  flex-wrap: wrap;
}
.socials__item {
  list-style: none;
}
.socials__link {
  text-transform: uppercase;
  color: $secondaryColor;
  transition: color 0.3s ease;
  &:hover {
    color: $primaryColor;
  }
}
</style>
