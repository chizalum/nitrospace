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
      <h3 class="join">Join the Revolution</h3>
      <p class="push">Push your limits, inspire change.</p>
      <button class="blog">BLOG</button>
    </div>

    <div class="image-grid">
    <div class="image-item" v-for="(image, index) in grid" :key="index">
      <img :src="image.url" :alt="image.alt">
      <p>{{ image.caption }}</p>
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
    return {
      activeNav: true,
      activeNav1: false,
      activeNav2: false,
      activeNav3: false,
      images: [
        require('@/assets/soccer-corner.jpg'),
        require('@/assets/stadium.jpg'),
        require('@/assets/football.jpg'),
        require('@/assets/american-football.jpg')
      ],
      timer: null,
      currentIndex: 0,
      grid: [
        {
          url: require('@/assets/soccer-corner.jpg'),
          alt: "Description of image 1",
          caption: "This is image 1"
        },
        {
          url: require('@/assets/soccer-corner.jpg'),
          alt: "Description of image 2",
          caption: "This is image 2"
        },
        {
          url: require('@/assets/soccer-corner.jpg'),
          alt: "Description of image 3",
          caption: "This is image 3"
        },
        {
          url: require('@/assets/soccer-corner.jpg'),
          alt: "Description of image 4",
          caption: "This is image 4"
        },
        {
          url: "https://example.com/image5.jpg",
          alt: "Description of image 5",
          caption: "This is image 5"
        },
        {
          url: require('@/assets/soccer-corner.jpg'),
          alt: "Description of image 6",
          caption: "This is image 6"
        }
      ]
    };
  },

  mounted() {
    this.startSlide();
  },

  methods: {
    changeNav() {
      if (this.activeNav) {
        this.activeNav = true;
        this.activeNav1 = false;
        this.activeNav2 = false;
        this.activeNav3 = false;
      }
    },
    changeNav1() {
      if (this.activeNav1) {
        this.activeNav = false;
        this.activeNav1 = true;
        this.activeNav2 = false;
        this.activeNav3 = false;
      }
    },
    changeNav2() {
      if (this.activeNav2) {
        this.activeNav = false;
        this.activeNav1 = true;
        this.activeNav2 = true;
        this.activeNav3 = false;
      }
    },
    changeNav3() {
      if (this.activeNav3) {
        this.activeNav = false;
        this.activeNav1 = false;
        this.activeNav2 = false;
        this.activeNav3 = true;
      }
    },

    startSlide() {
      this.timer = setInterval(this.next, 4000);
    },
    next() {
      this.currentIndex += 1;
    },
    prev() {
      this.currentIndex -= 1;
    }
  },

  computed: {
    currentImg() {
      return this.images[Math.abs(this.currentIndex) % this.images.length];
    }
  }
};
</script>

<style scoped>
.root-div {
  background: #000000ff;
  background-size: cover;
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
  height: 50px;
  width: 100%;
  background: #171a1fff;
  border-radius: 0px;
  box-shadow: 0px 0px 1px #171a1f, 0px 0px 2px #171a1f;
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
/* Hover */
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
}

.image-header {
  width: 100%;
  height: 770px;
}

.image-slide {
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.9;
}

.join{
  position: absolute; 
  top: 292px; 
  left: 132px; 
  width: auto; 
  height: auto; 
  font-family: Lexend; 
  font-size: 64px; 
  font-weight: 1000; 
  color: #ffffffff; 
  letter-spacing: -5;
  text-shadow: 1px 1px 1px black,
  -1px -1px 1px black;
  opacity: 1;
}

.push{
  position: absolute; 
  top: 470px; 
  left: 132px; 
  width: 1176px; 
  height: 36px; 
  font-family: Manrope;
  font-size: 24px; 
  font-weight: 1000; 
  color: rgb(250, 224, 224); 
  text-shadow: 1px 1px 1px black,
  -1px -1px 1px black;
}

.blog{
  position: absolute; 
  top: 560px; 
  left: 132px; 
  height: 52px; 
  width: 160px;
  padding: 0 20px; 
  display: flex; 
  align-items: center; 
  justify-content: center; 
  font-family: Manrope; 
  font-size: 18px; 
  font-weight: 800; 
  color: #FFFFFFFF; 
  background: #6D31EDFF; 
  opacity: 1; 
  border: none; 
  border-radius: 8px;
  box-shadow: 1px 1px 1px black,
  -1px -1px 1px black;
}

.blog:hover {
  color: #FFFFFFFF; 
  background: #5113D7FF; 
}

.image-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);  
  gap: 20px;           
  width: 80%;                   
  margin: 70px auto 0 auto;
}

.image-item {
  text-align: center;
}

.image-item img {
  width: 100%;      
  height: auto;      
  display: block;    
}
</style>
