<template>
  <div>
    <div class="gallery">
      <div v-for="(image, index) in images" :key="index" @click="openImage(image)">
        <img class="gallery-img" :src="image.thumbnail" alt="Gallery Image" />
        <div class="caption">{{ image.caption }}</div>
        <div class="author">{{ image.author }}</div>
      </div>
    </div>
    <image-modal v-if="modalOpen" :image="selectedImage" @close="closeImage" />
  </div>
</template>

<script>
import ImageModal from './ImageModal.vue';

export default {
  components: {
    'image-modal': ImageModal,
  },
  data() {
    return {
      images: [
        {
          thumbnail: require('@/assets/img/image1.jpeg'),
          fullSize: require('@/assets/img/image1.jpeg'),
          caption: 'forest1',
          author: 'author1',
        },
        {
          thumbnail: require('@/assets/img/image2.jpg'),
          fullSize: require('@/assets/img/image2.jpg'),
          caption: 'forest2',
          author: 'author2',
        },
        {
          thumbnail: require('@/assets/img/image3.jpg'),
          fullSize: require('@/assets/img/image3.jpg'),
          caption: 'forest3',
          author: 'author3',
        },
        {
          thumbnail: require('@/assets/img/image4.jpg'),
          fullSize: require('@/assets/img/image4.jpg'),
          caption: 'red panda',
          author: 'author4',
        },
        {
          thumbnail: require('@/assets/img/image5.jpg'),
          fullSize: require('@/assets/img/image5.jpg'),
          caption: 'wolf',
          author: 'author5',
        },
        {
          thumbnail: require('@/assets/img/image6.jpg'),
          fullSize: require('@/assets/img/image6.jpg'),
          caption: 'squirrel',
          author: 'author6',
        },
      ],
      modalOpen: false,
      selectedImage: null,
    };
  },
  methods: {
    openImage(image) {
      this.selectedImage = image;
      this.modalOpen = true;
    },
    closeImage() {
      this.selectedImage = null;
      this.modalOpen = false;
    },
  },
};
</script>

<style scoped>
.gallery {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  color: #fff;
}

.gallery-img {
  width: 200px;
  height: 150px;
  margin: 10px;
  cursor: pointer;
  border: 2px solid #ccc;
  transition: border-color 0.3s;
}

.gallery img:hover {
  border-color: #555;
}

.author {
  margin-bottom: 50px;
}
</style>
