<script setup>
import { RouterView } from 'vue-router'
import { onMounted, reactive } from 'vue';
const header_parameters = reactive({ width: "", height: "" });
onMounted(function set_positions() {
  header_parameters.width = window.innerWidth - 10 + "px";
  header_parameters.height = ((window.innerHeight / 100) * 20) + "px";
});
</script>

<template>
  <div id="header-container">
    <img class="header-button" src="./assets/headermain.png" />
    <img class="header-button" src="./assets/headerquestions.png" />
  </div>
  <div>
    <div id="main-info">
    </div>
    <div id="info-button">
    </div>
  </div>
  <div id="additional-byer-info">
    <div class="layer">
      <img class="art" src="./assets/cardwithart.png">
      <div id="buy-button">
        <img id="button-decorator" src="./assets/kitten.png" />
        <img id="button" src="./assets/buybutton.png" />
      </div>
    </div>
    <div class="layer">
      <img class="art" src="./assets/cardwithart2.png" />
      <div id="about-menu">
        <img class="about-button" src="./assets/reviews.png" />
        <img class="about-button" src="./assets/portfolio.png" />
      </div>
    </div>
  </div>
  <div id="basement">
    <img id="faq-button" src="./assets/faq.png">
    <div id="social">
      <img class="social-item" src="./assets/vk.png">
      <img class="social-item" src="./assets/discord.png">
      <img class="social-item" src="./assets/tg.png">
    </div>
  </div>
  <RouterView />
</template>

<style scoped>
#header-container {
  margin: auto;
  width: v-bind("header_parameters.width");
  max-width: v-bind("header_parameters.width");
  display: flex;
  justify-content: space-between;
}

.header-button {
  width: 50%;
}

#main-info {
  margin-top: 5%;
  padding: 3%;
  padding-left: 45px;
  padding-right: 15px;
  min-height: 200px;
  max-width: 75%;
  background-image: url("./assets/infoblue.png");
  background-size: cover;
}

#info-button {
  margin-left: 5%;
  min-height: 120px;
  max-width: 45%;
  background-image: url("./assets/infobluebutton.png");
  background-size: 100% 100%;
}

#additional-byer-info {
  padding-top: 20%;
  max-width: v-bind("header_parameters.width");
  min-height: 500px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
}

.layer {
  width: v-bind("header_parameters.width");
  display: flex;
  justify-content: space-evenly;
  align-items: end;
}

.art {
  width: 36%
}

#buy-button {
  position: relative;
  width: 40%;
}

#button-decorator {
  position: absolute;
  width: 70%;
  bottom: 75%;
  left: 10%;
}


#button {
  width: 100%;
  background-image: url("./assets/buttonbackground.png");
  background-size: 100% 100%;
}

#about-menu {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  max-width: 40%;
}

.about-button {
  width: 47%;
}

#basement {
  margin-top: 10%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  min-height: 50px;
  padding-left: 1%;
  padding-right: 1%;
  padding-top: 1%;
  background-image: url("./assets/basement.png");
  background-size: cover;
}

#faq-button {
  width: 10%;
}

#social {
  display: flex;
  flex-direction: row;
  justify-content: end;
  align-items: center;
}

.social-item {
  width: 15%
}
</style>
