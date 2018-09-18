<template>
    <div>
        <h3>This is coming from the Hello Component!</h3>
        <hr>
        <form>
            <input type="text" id="box" placeholder="Enter text to update title.." v-model="submitData">
            <input type="button" class="btn-primary" value="Click" @click="display">
        </form>
        <br>
        <p v-if="submitData.length > 0">{{ newTitle }}</p>
    </div>
</template>

<script>
export default {
  name: "Hello",
  data() {
    return {
      submitData: "",
      title: ""
    };
  },
  methods: {
    // when someone clicks the button, emit the submitData to the main component
    display(e) {
      this.$emit("displayData", this.submitData);

      e.preventDefault();
    }
  },
  computed: {
    newTitle() {
      return `This is going to be your new title: ${this.submitData}`;
    }
  }
};
</script>

<style scoped>
h3 {
  color: grey;
}
#box {
  width: 250px;
}
</style>
