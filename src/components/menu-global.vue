<template>
  <b-navbar>
    <template slot="brand">
      <b-navbar-item tag="router-link" to="/">
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/25/WebGL_Logo.svg" alt="WebGL" />
      </b-navbar-item>
    </template>
    <template slot="start">
      <b-navbar-item href="/">
        Home
      </b-navbar-item>
      <b-navbar-item href="/game">
        Game
      </b-navbar-item>
    </template>
  </b-navbar>
</template>
<script>
export default {
  name: "menu-global"
};
</script>
