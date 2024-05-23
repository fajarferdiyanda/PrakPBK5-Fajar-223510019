<template>
  <div class="carousel-container">
    <button class="nav prev" @click="prevSlide">‹</button>
    <div class="carousel">
      <transition-group name="carousel" tag="div" class="carousel-inner">
        <div
          v-for="(image, index) in images"
          :key="index"
          v-show="index === currentIndex"
          class="carousel-item"
        >
          <img :src="image.url" :alt="image.alt" />
        </div>
      </transition-group>
    </div>
    <button class="nav next" @click="nextSlide">›</button>
  </div>
</template>

<script>
export default {
  name: 'Carousel',
  data() {
    return {
      images: [
        {
          url: 'https://c.static-nike.com/a/images/f_auto/dpr_1.5,cs_srgb/w_1263,c_limit/tpqid8vgfey6m4ke86te/123-joyride-cdp-apla-xa-xp.jpg',
          alt: 'Joyride Sneakers'
        },
        {
          url: 'https://static.nike.com/a/images/w_960,c_limit/a2bd4535-c774-46f2-ac71-c4b74b78acf0/image.png',
          alt: 'Image 2'
        },
        {
          url: 'https://wallpapercave.com/uwp/uwp4382835.png',
          alt: 'Image 3'
        }
      ],
      currentIndex: 0
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.images.length) % this.images.length;
    }
  }
};
</script>

<style>
.carousel-container {
  position: relative;
  width: 80%;
  margin: auto;
  overflow: hidden;
  padding: 10px;
}

.carousel-inner {
  display: flex;
  transition: transform 0.5s ease-in-out;
}

.carousel-item {
  min-width: 100%;
  transition: transform 0.5s ease-in-out;
  flex: none;
  scroll-snap-align: start;
  border-radius: 8px;
  overflow: hidden;
}

.carousel-item img {
  width: 100%;
  max-height: 500px;
  object-fit: cover;
  border-radius: 8px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
}

.carousel-enter-active, .carousel-leave-active {
  transition: opacity 0.5s;
}
.carousel-enter, .carousel-leave-to /* .carousel-leave-active in <2.1.8 */ {
  opacity: 0;
}

.nav {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(255, 255, 255, 0.7);
  border: none;
  font-size: 2rem;
  cursor: pointer;
  padding: 0.5rem;
  z-index: 1;
  transition: background-color 0.3s;
}

.nav:hover {
  background-color: rgba(255, 255, 255, 0.9);
}

.nav.prev {
  left: 10px;
}

.nav.next {
  right: 10px;
}

@media (max-width: 768px) {
  .carousel-container {
    width: 100%;
  }
  .carousel-item {
    width: 90%;
  }
  .nav {
    font-size: 1.5rem;
  }
}
</style>
