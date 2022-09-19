<template>
  <div>
    <h3>Vue 3 change image URL with button click</h3>
    <button @click="showPreviousImage">Previous</button>
    <button @click="showNextImage">Next</button>
    <p>Image URL: {{ imageUrl }}</p>
    <div class="np-ht">
      <img :src="imageUrl" />
    </div>
    <!--
      www.nightprogrammer.com
    -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      imageId: 1,
    };
  },
  computed: {
    imageUrl() {
      return `https://picsum.photos/id/${this.imageId}/500/400`;
    },
  },
  methods: {
    showPreviousImage() {
      if (this.imageId > 1) this.imageId--;
    },
    showNextImage() {
      this.imageId++;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
button {
  border: 1px solid #000;
  min-width: 120px;
  margin: 10px;
  padding: 6px;
}
</style>
