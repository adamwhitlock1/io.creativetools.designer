<template>
  <div id="app">
    <!-- custom single file component -->
    <demo></demo>
    <button class="spectrum-ActionButton">
      <span class="spectrum-ActionButton-label">Edit</span>
    </button>
  </div>
</template>

<script>
// define single file component
import demo from "./assets/demo.vue";

export default {
  name: "app",

  // add to active components object
  components: { demo },

  created() {
    var csInterface = new CSInterface();
    var hostEnvironment = csInterface.getHostEnvironment();
    var appSkinInfo = hostEnvironment.appSkinInfo;

    switch (appSkinInfo.panelBackgroundColor.color.red) {
      case 50:
        console.log("Curent Theme: Darkest");
        document.getElementById("theme-styles").href =
          "./src/styles/spectrum-darkest.css";
        document.getElementById("app-body").classList.add("spectrum--darkest");
        break;

      case 83:
        console.log("Curent Theme: Dark");
        document.getElementById("theme-styles").href =
          "./src/styles/spectrum-dark.css";
        document.getElementById("app-body").classList.add("spectrum--dark");
        break;

      case 184:
        console.log("Curent Theme: Light");
        document.getElementById("theme-styles").href =
          "./src/styles/spectrum-light.css";
        document.getElementById("app-body").classList.add("spectrum--light");
        break;

      case 240:
        console.log("Curent Theme: Lightest");
        document.getElementById("theme-styles").href =
          "./src/styles/spectrum-lightest.css";
        document.getElementById("app-body").classList.add("spectrum--lightest");
        break;
    }
  },

  data() {
    return {
      msg: "Reactive text here"
    };
  }
};
</script>

<style>
#app {
  display: flex;
  height: 350px;
  width: auto;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

/* Scrollbar to match Adobe */
::-webkit-scrollbar {
  background: #2a2a2a;
}

::-webkit-scrollbar-thumb {
  background: #3e3e3e;
  border-radius: 20px;
}

::-webkit-scrollbar-thumb:hover {
  background: #525252;
}
</style>
