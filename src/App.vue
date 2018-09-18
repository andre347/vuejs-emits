<template>
    <div class="container">
        <h1>{{ title }}</h1>
        <hello-app v-on:displayData='updateDisplay($event)'></hello-app>
    </div>
</template>

<script>
import Hello from "./components/Hello.vue";

export default {
  components: {
    "hello-app": Hello
  },
  data() {
    return {
      title: "You can change me :)"
    };
  },
  methods: {
    // when someone click on the button the displayData function from the other component is emitted - this updateDisplay then picks it up and sets the title to something new
    updateDisplay: function(value) {
      this.title = value;
    }
  }
};
</script>

<style>
.container {
  padding: 10px;
  margin: 10px;
}
</style>
