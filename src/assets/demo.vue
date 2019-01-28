<template>
  <div id="test">
    <!-- Image needs absolute path in CEP -->
    <!-- <img src="./logo.png"> -->
    <h1>{{ msg }}</h1>

    <button class="spectrum-Button spectrum-Button--secondary">
      <span
        class="spectrum-Button-label"
        @click="startProgress"
      >start</span>
    </button>

    <input
      type="number"
      v-model="progress"
    >

    <div style="margin: 20px 0;">
      <div
        class="spectrum-BarLoader"
        role="progressbar"
      >
        <div class="spectrum-BarLoader-label">Loading</div>
        <div class="spectrum-BarLoader-percentage">{{progress}}%</div>
        <div class="spectrum-BarLoader-track">
          <div
            class="spectrum-BarLoader-fill"
            :style="{width: progress + '%'}"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "test",
  data() {
    return {
      msg: "Welcome to the future",
      progress: 0
    };
  },
  methods: {
    hello() {
      location.reload();
    },
    startProgress() {
      console.log("start progress");

      this.progress = 75;
    }
  }
};
</script>

<style>
</style>
