
<template>
  <div class="modal"  v-show="value">
    <div class="container">
    <span class="close" @click.prevent="close">&times;</span>

      <div class="modal__title">Direction</div>
      <p>Get a direction with your favourite apps</p>
      <a href="#" class="btn gmaps">
        <!-- <img src="https://img.icons8.com/color/420/google-maps.png"> Google Maps -->
      </a>
      <a href="#" class="btn waze">
        <!-- <img src="https://img.icons8.com/color/420/waze.png"> Waze -->
      </a>
      <button
        @click.prevent="close"
        class="mt-3 border-b border-teal font-semibold"
      >
        Close
      </button>
    </div>
  </div>
</template>

    <script>
export default {
  name: "Modal",
  props: {
    value: {
      required: true,
    },
  },
  methods: {
    close() {
      this.$emit("input", !this.value);
    },
  },
};
</script>


    <style lang="css" scoped>
.modal {
  background: rgba(0, 0, 0, 0.801);
  height: 100%;
  width: 100%;
  position: fixed;
  padding-top: 100px;
  z-index: 2;
  top:0;
  left:0;
}
.container {
  background: rgb(255, 255, 255);
  width: 70%;
  height: 50%;
  margin: auto;
  padding:20px;
}
/* The Close Button */
.close {
  color: #aaaaaa;
  float: right;
  font-size: 28px;
  font-weight: bold;
}

.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
}
</style>