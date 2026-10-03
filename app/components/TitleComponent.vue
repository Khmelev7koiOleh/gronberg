<script setup lang="ts">
defineProps<{
  titleOne: string;
  titleTwo: string;
}>();
import { useIntersection } from "@/composables/useIntersection";
const { target: titleTarget, isVisible: titleVisible } = useIntersection(0.15);
</script>
<template>
  <div
    class="title-component"
    ref="titleTarget"
    :class="{ 'is-show': titleVisible }"
  >
    <div class="title-component__title">
      <span>{{ titleOne }}</span>
      <span>{{ titleTwo }}</span>
    </div>

    <NuxtLink to="/" class="title-component__action">
      <div class="title-component__text">View All</div>

      <svg
        class="title-component__svg"
        width="32"
        height="15"
        viewBox="0 0 32 15"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path d="M0 7.35352H30" />
        <path d="M23.5 0.353516L30.5 7.35352L23.5 14.3535" />
      </svg>
    </NuxtLink>
  </div>
</template>

<style scoped lang="scss">
@use "@/assets/scss/style" as *;

.title-component {
  opacity: 0;
  max-width: 1400px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 20px;
  flex-wrap: wrap;
  padding-inline: 10px;
}

.title-component__title {
  display: flex;
  align-items: center;
  gap: 1rem;

  font-weight: 400;
  font-size: clamp(36px, 10vw, 100px);
  line-height: 110%;
  letter-spacing: 0px;
  color: $secondaryColor;
  text-transform: uppercase;
  span {
    &:nth-child(2) {
      color: $primaryColor;
      text-transform: none;
    }
  }
}
.title-component__action {
  display: flex;
  align-items: center;

  gap: 8px;

  &:hover .title-component__text {
    color: $primaryColor;
  }
  &:hover .title-component__svg {
    stroke: $primaryColor;
    cursor: pointer;

    transform: translateX(4px);
  }
}
.title-component__text {
  font-weight: 400;
  font-size: 16px;
  line-height: 160%;
  letter-spacing: 0px;
  color: $secondaryColor;
  text-transform: none;
  margin-right: 8px;
  transition: color 0.3s ease;
}
.title-component__svg {
  stroke: $secondaryColor;
  transition:
    stroke 0.3s ease,
    transform 0.3s ease;
}

.is-show {
  opacity: 1;
  transform: translateY(-50px);

  transition:
    opacity 1s ease,
    transform 1s ease;
}
</style>
