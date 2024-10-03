<template>
  <div class="image-grid">
    <div class="image-item" v-for="(image, index) in grid" :key="index">
      <p class="number">{{ image.caption }}</p>
      <div class="vertical-rule" ></div>
      <img :src="image.url" :alt="image.alt" />
      <p class="lorem">
        Lorem ipsum dolor sit amet consectetur, adipisicing elit. Harum numquam,
        veritatis unde obcaecati fuga animi similique consequuntur quis est
        iusto assumenda officiis. Nisi ipsa ad magnam id labore fugiat atque.
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Provident non
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      grid: [
        {
          url: require("@/assets/football.jpg"),
          alt: "Description of image 1",
          caption: "This is image 1",
        },
        {
          url: require("@/assets/kayak.jpg"),
          alt: "Description of image 2",
          caption: "This is image 2",
        },
        {
          url: require("@/assets/vehicles.jpg"),
          alt: "Description of image 3",
          caption: "This is image 3",
        },
        {
          url: require("@/assets/headline-photos/headline9.jpg"),
          alt: "Description of image 4",
          caption: "This is image 4",
        },
        {
          url: require("@/assets/headline-photos/headline3.jpg"),
          alt: "Description of image 5",
          caption: "This is image 5",
        },
        {
          url: require("@/assets/headline-photos/headline12.jpg"),
          alt: "Description of image 6",
          caption: "This is image 6",
        },
      ],
    };
  },
};
</script>


<style scoped>
.image-grid {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 640px;
  margin: 0 auto 0 auto;
  justify-content: start;
  padding: 0;
  overflow-y: scroll;
  overflow-x: scroll;
  scroll-behavior: smooth;
}

.image-item {
  margin: 0;
  padding: 0;
  width: 80%;
  height: auto;
  border-radius: 16px;
  transform-origin: center;
  display: flex;
  flex-direction: column;
  background: 
 rgba(79, 78, 78, 0.1)
  ;
  backdrop-filter: blur(10px);
  -webkit-backdrop-filter: blur(10px);

  box-shadow: 0 8px 22px 0 rgba(114, 113, 113, 0.37);
}

.image-item img {
  width: 65%;
  height: 30%;
  min-height: 170px;
  border-radius: 16px;
  border: none;
  margin: 0;
  padding: 0;
}

.image-item:nth-child(odd) {
  margin: 0;
  align-items: flex-start;
  padding: 0;
}

.image-item:nth-child(even) {
  align-self: flex-end;
  align-items: flex-end;
  margin: 80px 0;
  padding: 0;
}

.vertical-rule {
  border-left: 6px solid green;
  height: 50px;
  position: absolute;
  left: 50%;
  margin-left: -3px;
  top: 0;
}

.lorem {
  color: wheat;
  word-wrap: break-word;
  overflow-wrap: break-word;
  white-space: normal;
  margin: 0;
  width: 100%;
}

.number {
  color: wheat;
  word-wrap: break-word;
  overflow-wrap: break-word;
  white-space: normal;
  margin: 0;
  width: 100%;
}
</style>