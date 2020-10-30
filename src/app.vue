<template>
  <div id="app">
    <menu-global />
    <router-view />
  </div>
</template>
<script>
import MenuGlobal from "@/components/menu-global";

export default {
  components: { MenuGlobal }
};
</script>
