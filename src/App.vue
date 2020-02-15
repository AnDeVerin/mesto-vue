<template>
  <div class="root">
    <header class="header root__section">
      <img src="./assets/images/logo.svg" alt="mesto logo" class="logo" />
    </header>

    <div class="profile root__section">
      <div class="user-info">
        <div class="user-info__photo"></div>
        <div class="user-info__data">
          <h1 class="user-info__name">Jaques Causteau</h1>
          <p class="user-info__job">Sailor, Researcher</p>
        </div>
        <button class="button user-info__button">+</button>
      </div>
    </div>

    <div class="places-list root__section"></div>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
@import url(./assets/pages/index.css);
</style>
