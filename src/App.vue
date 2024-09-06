<template>
  <div class="root-div">
    <div class="first-flex">
      <div class="flex-child1">
        <h1 class="title">
          BLAC
          <span class="span-1">- Design & Build</span>
        </h1>
      </div>
      <div class="flex-child2">
        <img src="@/assets/facebook.svg" class="facebook" />
        <img src="@/assets/x.svg" class="twitter" />
        <a href="https:/instagram.com/blac.lyfe" target="blank" class="link">
          <img src="@/assets/instagram.svg" class="instagram" />
        </a>
      </div>
    </div>
    <div class="second-flex">
      <div class="image-house">
        <img src="@/assets/kayak.jpg" class="image1" />
      </div>
      <div class="image-house2">
        <img src="@/assets/dirt-bike.jpg" class="image2" />
      </div>
      <div class="text-house">
        <p class="projects">Projects</p>
        <h2 class="blac">BLAC AGENCY</h2>
        <h3 class="lorem">Dream Tournament 2024</h3>
        <p class="euro">European Football Scouting Tournament</p>
        <p class="read"><span class="plus">+</span> Read More</p>
      </div>
    </div>
    <div class="third-flex">
      <div class="image-holder">
        <img src="@/assets/vehicles.jpg" class="pic" />
      </div>
      <div class="image-holder2">
        <img src="@/assets/agama.jpg" class="pic1" />
      </div>
    </div>
    <Home class="Home"></Home>
  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "App",
  components: { Home },
  data() {
    return {};
  },
};
</script>

<style scoped>

.root-div {
  background: #d8c9c9;
  height: 100%;
  top: 0;
  left: 0;
  width: 100vw;
  z-index: 999;
  margin: 0;
  padding: 0;
  animation: fadeInAnimation ease-out 2s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

@keyframes fadeInAnimation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

.first-flex {
  margin: 0;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 50px;
  width: 100%;
  background: rgb(244, 244, 251);
}

.flex-child1 {
  width: auto;
  margin: auto 0 auto 50px;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}
.flex-child2 {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  align-items: center;
  width: 200px;
  height: 100%;
  margin: auto 0 auto 0;
}
.title {
  font-family: arial;
  font-size: 30px;
  color: black;
  font-weight: bolder;
  border-bottom: 2px solid black;
}

.span-1 {
  font-family: "Courier New", Courier, monospace;
  font-size: 15px;
  color: rgb(79, 121, 6);
  animation: write 3s steps(90, end);
}

@keyframes write {
  0% {
    font-size: 2px;
  }
  50% {
    font-size: 8px;
  }
  100% {
    font-size: 15px;
  }
}

.facebook {
  height: 20px;
  width: 30px;
  margin: 0;
}

.twitter {
  height: 20px;
  width: 30px;
  margin: 0;
}

.instagram {
  height: 23px;
  width: 30px;
  margin: 4px 0 0 0;
}

.link {
  margin: 0;
  padding: 0;
}

.second-flex {
  display: flex;
  flex-direction: row;
  width: auto;
  height: auto;
  justify-content: space-between;
  align-items: start;
  margin: 100px 50px 0 50px;
  padding: 0;
}
.image-house {
  width: 38%;
  height: 100%;
  margin: auto 0 auto 0;
  padding: 0;
}

.image1 {
  width: 100%;
  margin: 0;
  height: 420px;
  border-radius: 6px;
}

.image-house2 {
  width: 28%;
  height: 100%;
  margin: auto 0 auto 0;
  padding: 0;
}

.image2 {
  width: 100%;
  margin: 0;
  height: 420px;
  border-radius: 6px;
}

.text-house {
  width: 28%;
  height: 420px;
  margin: 0 0 0 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  align-items: start;
  justify-content: space-evenly;
  flex-wrap: wrap;
}

.projects {
  margin: 0 0 0 0;
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  font-size: 25px;
  font-weight: bold;
  color: rgb(80, 56, 12);
  border-bottom: 2px solid rgb(117, 103, 103);
}

.blac {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 45px;
  color: black;
  margin: 0;
  font-weight: bold;
}

.lorem {
  font-family: arial;
  font-size: 38px;
  color: rgb(78, 2, 2);
  margin: 0;
}

.euro {
  font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  font-size: 20px;
  word-wrap: break-word;
  color: rgb(78, 2, 2);
  margin: 0;
}

.read {
  color: rgb(79, 121, 6);
  font-family: "Courier New", Courier, monospace;
  font-size: 20px;
  margin: 0;
  padding: 0;
  animation: bounce ease-in-out 4s;
  animation-iteration-count: infinite;
  animation-fill-mode: forwards;
}

.plus{
  font-size: 35px;
  margin: 0;
}

@keyframes bounce {
  0% {
    opacity: 0.2;
  }
  100% {
    opacity: 1;
  }
}

.third-flex {
  display: flex;
  flex-direction: row;
  width: auto;
  height: auto;
  justify-content: space-between;
  align-items: start;
  margin: 30px 50px 0 50px;
  padding: 0;
}

.image-holder {
  width: 54%;
  height: 100%;
  margin: auto 0 auto 0;
  padding: 0;
}

.image-holder2 {
  width: 42%;
  height: 100%;
  margin: auto 0 auto 0;
  padding: 0;
}

.pic {
  width: 100%;
  margin: 0;
  height: 420px;
  border-radius: 6px;
}

.pic1 {
  width: 100%;
  margin: 0;
  height: 420px;
  border-radius: 6px;
}
</style>
