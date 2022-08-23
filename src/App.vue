<template>
  <div :class="computedContainerClass" class="container">
    <div  class="no-transit">
      <div :class="computedTranslateClass"  class="all_logo">
        <div v-for="language in languages" :key="language" :ref="language"
             :class="`${language}_divs`" >
          <img  :src="`img/${language}.jpg`" alt="" class="logo" >
          <div :class="`${language}_divs`">
            <div class="long"></div>
            <div class="short"></div>
            <div class="long"></div>
          </div>
        </div>
      </div>
      <div class="buttons">
        <img @click="selectedLang = logo" :class="{'img_max': selectedLang === logo}" v-for="logo in languages" :key="logo" :src="`img/${logo}.jpg`" :alt="logo"
             class="btn_logo" >
      </div>
    </div>
  </div>


</template>

<script>
export default {
  name: 'App',
  components: {},
  data() {
    return {
      languages: ["html", "css", "js", "react"],
      selectedLang: 'html'
    }
  }
  ,
  computed: {
    computedContainerClass() {
      if (this.selectedLang === "html") return "body_coral";
      if (this.selectedLang === "css") return "body_orange";
      if (this.selectedLang === "js") return "body_yellow";
      if (this.selectedLang === "react") return "body_yellow_green";
      return "body_coral";
    },
    computedTranslateClass() {
      if (this.selectedLang === "html") return "translate_left_html";
      if (this.selectedLang === "css") return "translate_left_css";
      if (this.selectedLang === "js") return "translate_left_js";
      if (this.selectedLang === "react") return "translate_left_react";
      return "body_left_react";
    },
  },
  methods: {}
}

</script>

<style>
* {
  transition: 1s ease;
}

.html_divs {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.css_divs {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.js_divs {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.react_divs {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.long {
  margin: 20px;
  width: 300px;
  height: 5px;
  background-color: grey;
  border-radius: 35px;
}

.short {
  width: 150px;
  height: 5px;
  background-color: grey;
  border-radius: 35px;
}

.logo {
  width: 100px;
}

.no-transit {
  display: flex;
  flex-direction: column;
  background-color: white;
  width: 340px;
  overflow: hidden;
  height: 450px;
}

.all_logo {
  display: flex;
  position: relative;
  padding-top: 85px;

}

.btn_logo {
  width: 50px;
}

.buttons {
  padding-top: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  padding: 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  align-content: center;
  background: no-repeat;
  height: 100%;
  width: 100%;
}

.translate_left_html {
  transform: translateX(1px);
}

.translate_left_css {
  transform: translateX(-345px);
}

.translate_left_js {
  transform: translateX(-680px);
}
.translate_left_react {
  transform: translateX(-1020px);
}

.body_coral {
  height: 100vh;
  background: rgba(34, 195, 123);
  background: linear-gradient(0deg, rgba(34, 195, 123, 1) 0%, rgba(152, 45, 253, 1) 100%);
}

.body_orange {
  height: 100vh;
  background: rgb(36, 16, 0);
  background: linear-gradient(90deg, rgba(36, 16, 0, 1) 0%, rgba(121, 89, 9, 1) 35%, rgba(255, 0, 0, 1) 100%);
}

.body_yellow {
  height: 100vh;
  background: rgb(180, 133, 58);
  background: linear-gradient(90deg, rgba(180, 133, 58, 1) 0%, rgba(253, 29, 29, 1) 50%, rgba(236, 252, 69, 1) 100%);
}

.body_yellow_green {
  height: 100vh;
  background: rgb(89, 251, 63);
  background: radial-gradient(circle, rgba(89, 251, 63, 1) 0%, rgba(252, 250, 70, 1) 100%);
}

.img_max {
  width: 60px;
  border-radius: 25px;
  transform: rotate(1turn);
}
body {
  margin: 0;
}
</style>
