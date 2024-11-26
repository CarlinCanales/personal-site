<script setup>
import { ref } from 'vue';

const isOpen = ref(true);

function handleTogglePortfolio() {
  isOpen.value = !isOpen.value;
}

</script>

<template>
  <article class="portfolio-navigator" :class="{'portfolio-navigator--opened': isOpen}">
    <button class="portfolio-navigator__container" @click="handleTogglePortfolio">
      <span class="portfolio-navigator__title">Portfolio</span>
      <ul class="portfolio-navigator__list">
        <li><a href="">ToDo - coming soon</a></li>
        <li>Math Helper - coming soon</li>
        <li>Selanac Bank - coming soon</li>
        <li>Payments API - coming soon</li>
      </ul>
    </button>
  </article>
</template>

<style scoped lang="scss">
$transition-values: .1s ease-in-out;
.portfolio-navigator {
  position: fixed;
  bottom: 2rem;
  right: 2rem;

  &--opened &__title {
    margin-bottom: 1rem;
  }

  &__container {
    border-radius: 50%;
    width: 8rem;
    aspect-ratio: 1;
    border: .5rem solid var(--yankee-navy);
    background-color: var(--yankee-gray);

    font-weight: bold;
    cursor: pointer;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    padding: 0;

    transition: width $transition-values, border-radius $transition-values;
  }

  &--opened &__container {
    border-radius: 10%;
    width: 15rem;
  }

  &__list {
    display: none;
  }

  &--opened &__list {
    display: block;
    padding: 0;
    margin: 0;
    list-style: none;
    text-align: left;
    width: 100%;

    li:first-child {
      border-top: .13rem solid var(--yankee-navy);
    }

    li {
      padding: .5rem;
      margin-bottom: .5rem;
      border-bottom: .13rem solid var(--yankee-navy);
    }
  }

}
</style>
