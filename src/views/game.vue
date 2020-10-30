<template>
  <div>
    <div ref="viewport" class="viewport"></div>
    <b-button @click="rotate">Rotate the cube!!</b-button>
  </div>
</template>
<script>
import * as THREE from "three/build/three.module";

export default {
  name: "game",
  data() {
    return {
      camera: null,
      scene: null,
      geometry: null,
      mesh: null,
      renderer: null
    };
  },
  created() {
    this.scene = new THREE.Scene();
    this.geometry = new THREE.BoxGeometry(0.2, 0.2, 0.2);
    this.mesh = new THREE.Mesh(this.geometry, this.material);
    this.renderer = new THREE.WebGLRenderer({ antialias: true });
  },
  mounted() {
    const { viewport } = this.$refs;

    this.camera = new THREE.PerspectiveCamera(
      70,
      viewport.offsetWidth / viewport.offsetHeight,
      0.01,
      10
    );
    this.camera.position.z = 1;
    this.scene.add(this.mesh);
    this.renderer.setSize(viewport.offsetWidth, viewport.offsetHeight);
    viewport.appendChild(this.renderer.domElement);
    this.redraw();
  },
  methods: {
    rotate() {
      this.mesh.rotation.x += 0.4;
      this.mesh.rotation.y += 0.4;

      this.redraw();
    },
    redraw() {
      this.renderer.render(this.scene, this.camera);
    }
  }
};
</script>
<style lang="scss" scoped>
.viewport {
  height: 400px;
}
</style>
