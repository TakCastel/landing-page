<template>
  <div class="card banner-item" @click="handleClick">
    <img class="thumbnail-hovered" :src="hoveredThumbnail" :alt="alternativeText">
    <img class="thumbnail" :src="backgroundImage" :alt="alternativeText">
  </div>
</template>

<script>
export default {
  props: {
    redirectionLink: {
      type: String,
      default: '',
      required: true
    },
    backgroundImage: {
      type: String,
      default: '',
      required: true
    },
    alternativeText: {
      type: String,
      default: '',
      required: true
    },
    hoveredThumbnail: {
      type: String,
      default: '',
      required: true
    }
  },

  methods: {
    handleClick() {
      location.href = this.redirectionLink
    }
  }
}
</script>

<style scoped>
.card {
  cursor: pointer;
  position: relative;
}

.card img {
  width: 100%;
  height: auto;
  left: 0
}

.thumbnail, .thumbnail-hovered {
  position: absolute;
}

.thumbnail {
transition: opacity .3s;
}

.thumbnail:hover {
  opacity: 0
}
</style>