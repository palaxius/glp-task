<template>
  <div>
    <div class="navbar__top">
      <div class="navbar__top-left">
        <img src="../assets/menu.png" alt="menu" class="navbar__top-menu">
        <img src="../assets/logo.png" alt="logo" class="navbar__top-logo">
        <h1 class="navbar__top-title">Диспетчерская</h1>
      </div>
      <div class="navbar__top-right">
        <button class="navbar__top-btn">
          Администратор 1
        </button>
      </div>
    </div>
    <div class="wrapper">
      <div class="navbar__side">
        <img src="../assets/settings.png" alt="settings" class="navbar__side-settings settings-active">
      </div>
      <slot />
    </div>
  </div>
</template>