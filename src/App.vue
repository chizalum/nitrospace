<template>
  <div class="root-div">
    <div class="first-flex">
      <div class="flex-child1">
        <h1 class="title">BLAC.</h1>
      </div>
      <div class="flex-child2">
        <h2 class="home" :class="{ active: activeNav }" @click="changeNav()">
          Home
        </h2>
        <h2
          class="about"
          :class="{ active1: activeNav1 }"
          @click="changeNav1()"
        >
          About Us
        </h2>
        <h2
          class="service"
          :class="{ active2: activeNav2 }"
          @click="changeNav2()"
        >
          Services
        </h2>
        <h2
          class="event"
          :class="{ active3: activeNav3 }"
          @click="changeNav3()"
        >
          Events
        </h2>
      </div>
      <div class="flex-child3">
        <button class="button1">Get In Touch</button>
      </div>
    </div>
    <div class="image-header">
      <img :src="currentImg" class="image-slide" />
      <div class="first-blur">
      <div class="first-absolute">
        <h3 class="join">Join the Revolution</h3>
        <p class="push">Push your limits, inspire change.</p>
        <button class="blog">BLOG</button>
      </div>
      </div>
    </div>
    <div class="partner-div">
      <div class="partner-child1">
        <h3 class="partner-text">Our Valued Partners</h3>
      </div>
      <div class="partner-child2">
        <div class="partner-row">
          <p class="member-partner">Nitrospace</p>
          <p class="member-partner">NFF</p>
          <p class="member-partner">Mma Health&Welless</p>
        </div>
      </div>
    </div>
    <div class="insert-home">
      <div class="home2">
        <p>
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. At maxime
          repudiandae quam velit consequatur! Eius cum asperiores, omnis
          voluptas laborum saepe minima dolores odit, unde velit libero?
          Aspernatur, labore eveniet. Lorem ipsum, dolor sit amet consectetur
          adipisicing elit. Temporibus atque corporis nulla soluta vero culpa
          perferendis veniam, corrupti inventore consectetur rem voluptate ea
          maiores dolor velit laboriosam mollitia repellendus similique!
        </p>
      </div>
      <div class="home1">
        <Home class="imported-home"></Home>
      </div>
    </div>
  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "App",
  components: {
    Home,
  },
  data() {
    return {
      activeNav: true,
      activeNav1: false,
      activeNav2: false,
      activeNav3: false,
      images: [
        require("@/assets/headline-photos/headline.jpg"),
        require("@/assets/headline-photos/headline19.jpg"),
        require("@/assets/headline-photos/headline4.jpg"),
        require("@/assets/headline-photos/headline6.jpg"),
        require("@/assets/headline-photos/headline18.jpg"),
        require("@/assets/headline-photos/headline10.jpg"),
        require("@/assets/headline-photos/headline14.jpg"),
        require("@/assets/headline-photos/headline15.jpg"),
      ],
      timer: null,
      currentIndex: 0,
    };
  },

  mounted() {
    this.startSlide();
  },

  methods: {
    changeNav() {
      this.activeNav = true;
      this.activeNav1 = false;
      this.activeNav2 = false;
      this.activeNav3 = false;
    },
    changeNav1() {
      this.activeNav = false;
      this.activeNav1 = true;
      this.activeNav2 = false;
      this.activeNav3 = false;
    },
    changeNav2() {
      this.activeNav = false;
      this.activeNav1 = false;
      this.activeNav2 = true;
      this.activeNav3 = false;
    },
    changeNav3() {
      this.activeNav = false;
      this.activeNav1 = false;
      this.activeNav2 = false;
      this.activeNav3 = true;
    },

    startSlide() {
      this.timer = setInterval(this.next, 4000);
    },
    next() {
      this.currentIndex += 1;
    },
    prev() {
      this.currentIndex -= 1;
    },
  },

  computed: {
    currentImg() {
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    },
  },
};
</script>

<style scoped>
body{
  font-family: 'Inter', 'Inter-Italic', sans-serif;
}
.root-div {
  min-height: 100vh;
  top: 0;
  left: 0;
  min-width: 100vw;
  z-index: 999;
  margin: 0;
  padding: 0;
  animation: fadeInAnimation ease-out 2s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

.first-flex {
  margin: 0;
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  width: 100%;
  background: #171a1fff;
  border-radius: 0px;
  box-shadow: 0px 0px 1px #171a1f, 0px 0px 2px #171a1f;
  position: fixed;
  z-index: 999;
}

.flex-child1 {
  width: 20%;
  margin: auto 0 auto 0;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
  padding: 0 0 0 25px;
}
.flex-child2 {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-evenly;
  align-items: flex-start;
  width: 45%;
  height: 100%;
  margin: auto 0 auto 0;
}

.flex-child3 {
  width: 35%;
  margin: auto 0 auto 0;
  height: 100%;
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-items: center;
  padding: 0 25px 0 0;
}

.button1 {
  width: 160px;
  height: 36px;
  padding: 0 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: Manrope;
  font-size: 14px;
  line-height: 22px;
  font-weight: 400;
  color: #ffffffff;
  background: #6d31edff;
  opacity: 1;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

.button1:hover {
  color: #ffffffff;
  background: #5113d7ff;
  cursor: pointer;
}

.home {
  font-family: Manrope;
  font-size: 16px;
  line-height: 22px;
  font-weight: 700;
  color: #9f79f3ff;
  background: #000000ff;
  cursor: pointer;
}

.about {
  font-family: Manrope;
  font-size: 14px;
  line-height: 22px;
  font-weight: 400;
  color: #a8adb7ff;
  cursor: pointer;
}

.about:hover {
  color: rgb(231, 223, 249);
  background: #000000ff;
}
.active {
  color: #9f79f3ff;
  font-size: 16px;
}

.active1 {
  color: #9f79f3ff;
  font-size: 16px;
}

.active2 {
  color: #9f79f3ff;
  font-size: 16px;
}

.active3 {
  color: #9f79f3ff;
  font-size: 16px;
}
.service {
  font-family: Manrope;
  font-size: 14px;
  line-height: 22px;
  font-weight: 400;
  color: #a8adb7ff;
  cursor: pointer;
}

.event {
  font-family: Manrope;
  font-size: 14px;
  line-height: 22px;
  font-weight: 400;
  color: #a8adb7ff;
  cursor: pointer;
}

.title {
  font-family: Lexend arial;
  font-size: 28px;
  line-height: 42px;
  font-weight: 700;
  color: #ffffffff;
  letter-spacing: 4px;
}

.image-header {
  width: 100%;
  min-height: 770px;
  height: 80vh;
  position: relative;
}

.image-slide {
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.9;
  box-shadow: 0px 0px 1px #171a1f, 0px 0px 2px #171a1f;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0), #171a1fff);
}

.first-blur{
  background: rgba(79, 78, 78, 0.1);
  backdrop-filter: blur(5px);
  -webkit-backdrop-filter: blur(10px);
  box-shadow: 0 8px 22px 0 rgba(114, 113, 113, 0.37);
  height: 100%;
  width: 44%;
  position: absolute;
  top: 0;
  left: 0;
  margin: 0 auto 0 auto;
}

.first-absolute {
  position: absolute;
  top: 292px;
  left: 132px;
  margin: 0 auto 0 auto;
}

.join {
  width: auto;
  height: auto;
  font-family: Lexend;
  font-size: 64px;
  font-weight: 1000;
  color: #ffffffff;
  letter-spacing: -5;
  text-shadow: 1px 1px 1px black, -1px -1px 1px black;
  opacity: 1;
}

.push {
  width: 1176px;
  height: 36px;
  font-family: Manrope;
  font-size: 24px;
  font-weight: 1000;
  color: rgb(245, 243, 243);
  text-shadow: 1px 1px 1px black, -1px -1px 1px black;
}

.blog {
  height: 52px;
  width: 160px;
  padding: 0 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: Manrope;
  font-size: 18px;
  font-weight: 800;
  color: #ffffffff;
  background: #6d31edff;
  opacity: 1;
  border: none;
  border-radius: 8px;
  box-shadow: 1px 1px 1px black, -1px -1px 1px black;
}

.blog:hover {
  color: #ffffffff;
  background: #5113d7ff;
}

.partner-div {
  height: 80vh;
}

.partner-child1 {
  width: 100%;
  margin: 0;
  height: 40%;
}

.partner-text {
  font-family: 'Inter-Italic', sans-serif;
  font-optical-sizing: auto;
  font-size: 60px;
  font-weight: 600;
  font-style: normal;
  color: white;
}

.partner-child2 {
  width: 100%;
  margin: 0;
  height: 60%;
}

.partner-row {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  width: 100%;
}

.member-partner {
  font-family: 'Inter-Italic';
  font-optical-sizing: auto;
  font-size: 19px;
  font-weight: 600;
  font-style: normal;
  color: white;
}

.insert-home {
  width: 100%;
  height: 640px;
  margin: 30px 0 0 0;
  display: flex;
  flex-direction: row;
  overflow-x: scroll;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: start;
}

.home2 {
  margin: 0;
  padding: 0;
  width: 56%;
  height: 100%;
  background: #171a1fff;
  border-radius: 0px;
  box-shadow: 0px 0px 1px #171a1f, 0px 0px 2px #171a1f;
  background: linear-gradient(to bottom, rgba(255, 255, 255, 0), #171a1fff),
    url("@/assets/football.jpg");
  background-size: cover;
  background-position: center;
}

.second-imagehead {
  width: 100%;
  height: 100%;
}

.home1 {
  animation: ship 0.8s ease-in forwards;
  width: 44%;
  margin: 0 auto 0 auto;
  justify-content: center;
  background: #171a1fff;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);
  border: 3px solid #171a1fff;
}

.imported-home {
  margin: 70px auto 0 auto;
  width: 90%;
  justify-content: start;
}

@keyframes ship {
  0% {
    transform: translateY(-12%);
    opacity: 0.1;
  }
  25% {
    transform: translateY(-9%);
    opacity: 0.3;
  }
  50% {
    transform: translateY(-6%);
    opacity: 0.5;
  }
  75% {
    transform: translateY(-3%);
    opacity: 0.7;
  }
  100% {
    transform: translateY(0%);
    opacity: 1;
  }
}
</style>
