<template>
  <div id="app">
    <transition name="appear" mode="out-in">
      <component v-bind:is="component">
      </component>
    </transition>
  </div>
</template>

<script>
import Loader from "../components/Loader";
import MainContent from "../components/MainContent";
export default {
  name: "Main",
  components: {
    Loader: Loader,
    MainContent: MainContent,
  },
  data() {
    return {
      component: "Loader",
    };
  },
  // NOTE: Utiliser le pouvoir de Nuxt avec SEO
  // head() {
  //   let currentTitle = "";
  //   this.component === "Loader"
  //     ? (currentTitle = "Loading...")
  //     : (currentTitle = "Gil's Portfolio Website");

  //   return {
  //     title: currentTitle,
  //     meta: [
  //       {
  //         name: "My Portfolio site",
  //         content: "This is the main page to my website portfolio"
  //       }
  //     ]
  //   };
  // },
  mounted() {
    const imgs = document.querySelectorAll("img");
    console.log(imgs);
    window.addEventListener("load", () => {
      setTimeout(() => {
        this.component = "MainContent";
      }, 3000);
    });
  },
};
</script>

<style>
#app {
  height: 100%;
}

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.appear-enter-active {
  animation: appear 1s;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
