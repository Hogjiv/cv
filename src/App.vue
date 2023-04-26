<script>
import contactPage from "@/components/contactPage.vue";
import skillsPage from "@/components/skillsPage.vue";
import linksPage from "@/components/linksPage.vue";
import educationPage from "@/components/educationPage.vue";
import expiriencePage from "@/components/expiriencePage.vue";

export default {
  data() {
    return {
      scrollPosition: null,
    };
  },
  components: {
    contactPage,
    linksPage,
    skillsPage,
    educationPage,
    expiriencePage,
  },
  methods: {
    updateScroll() {
      this.scrollPosition = window.scrollY;
    },
  },
  mounted() {
    window.addEventListener("scroll", this.updateScroll);
  },
};
</script>

<template>
  <!-- Desktop version  -->
  <div class="main-container d-none col-md-5 d-md-flex">
    <div class="conten-top d-flex justify-content-center align-items-center">
      <h1>
        IRINA AVDEYEVA
        <br />
        web developer
      </h1>
      <div class="d-flex flex-row move">
        <div class="content-left d-flex flex-column align-items-center col-12">
          <div class="photo">
            <img src="../public/photo.jpg" class="photo" />
            <p class="mt-4 italic font-700">
              As a web developer, I believe it is essential to not only create
              effective and user-friendly websites but also to strive for their
              usefulness and relevance to society.
            </p>
            <contactPage> </contactPage>
          </div>
        </div>
        <div class="content">
          <div class="mt-5 mx-5">
            <linksPage> </linksPage>
            <skillsPage> </skillsPage>
            <expiriencePage> </expiriencePage>
            <educationPage class="mt-2"> </educationPage>
          </div>
        </div>
      </div>
    </div>
  </div>
  <!-- Mobile version  -->
  <div class="d-md-flex d-md-none flex-column d-flex pb-5">
    <div
      class="content-top-mob justify-content-center align-items-center d-flex position-fixed pt-3 pb-3"
    >
      <h1 class="font-45" :class="{ changeColor: scrollPosition > 50 }">
        IRINA AVDEYEVA
      </h1>
    </div>
    <div
      class="content-left-mob justify-content-center align-items-center d-flex flex-column pb-4"
    >
      <div class="photo-mob align-items-center d-flex justify-content-center">
        <img src="../public/photo.jpg" class="photo-mob"/>
      </div>
      <p class="mt-5 italic font-700 mx-4 font-18">
        As a web developer, I believe it is essential to not only create
        effective and user-friendly websites but also to strive for their
        usefulness and relevance to society.
      </p>
      <contactPage class="text-center"> </contactPage>
    </div>
    <div class="mx-4 mt-4">
      <linksPage> </linksPage>
      <skillsPage> </skillsPage>
      <expiriencePage> </expiriencePage>
      <educationPage> </educationPage>
    </div>
  </div>
</template>

<style lang="scss">
@import "bootstrap/scss/bootstrap.scss";
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,300;0,700;1,300&display=swap");

.main {
  background-color: #91aead;
  width: 340px;
  height: 400px;
}
body {
  background-color: rgb(222, 222, 222);
  color: #2d2d2d;
}
a, p {
  font-family: "Roboto", sans-serif;
  font-weight: 300;
  color: rgb(0, 0, 0);
}
h5 {
  font-weight: 700;
}
.italic {
  font-family: "Roboto", sans-serif;
  font-style: italic;
}
.font-700 {
  font-weight: 700;
}
.font-45 {
  font-size: 45px;
}
.font-18 {
  font-size: 18px;
}
.text-gray {
  color: rgb(215, 215, 215) !important;
}

// Main containers
.main-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}
.content {
  right: 0px;
  width: 800px;
  overflow-y: auto;
  overflow-x: hidden;
  max-height: 600px;
  margin-top: 220px;
}
.conten-top {
  background-color: #cebba3;
  width: 1300px;
  height: 200px;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  margin-top: 50px;
}
.content-left {
  background-color: #91aead;
  width: 350px;
  height: 830px;
  overflow: hidden;
}
.block a {
  color: #b7a490 !important;
  text-decoration: none !important;
  font-weight: 700;
}
.block a:hover {
  color: #7a989f !important;
  text-decoration: none;
  font-weight: 700;
}
.photo {
  width: 230px;
  height: 230px;
  border-radius: 50%;
  margin-top: 20px;
}
.move {
  position: absolute;
  margin-top: 600px;
  overflow: hidden;
}

p:not(.main-container p) {
  color: rgb(78, 78, 78);
  font-style: italic;
}

// buttons
.resume-button {
  text-decoration: none !important;
  color: #ffffff;
}
.download {
  background-color: #7ca7a5 !important;
}
.download:hover {
  box-shadow: 0px 0px 8px #7ca7a5;
  box-shadow: 0px 0px 15px #7ca7a5;
}
.btn {
  width: 200px;
  height: 40px;
  margin-bottom: 20px;
}
// Mobile
.content-top-mob {
  background-color: #cebba3;
  width: 100%;
}
.photo-mob {
  width: 330px;
  height: 330px;
  border-radius: 50%;
}
.mob {
  background-color: #646464b8;
  height: 400px;
  width: 300px;
}
.content-left-mob {
  background-color: #91aead;
  padding-top: 130px;
}
// JS
.changeColor {
  color: rgba(154, 154, 154, 0.8);
}
// scroll 
::-webkit-scrollbar {
  width: 20px;
}
::-webkit-scrollbar-thumb {
  background-color: rgba(199, 185, 156, 0.3);
  border-radius: 5px;
}
::-webkit-scrollbar-button {
  display: none;
}
::-webkit-scrollbar-track {
  background-color: transparent;
}
</style>
