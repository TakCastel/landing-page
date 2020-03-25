<template>
  <div class="game" @click="handleClick" :class="{ disabled: isDisabled }">
    <img :src="backgroundImage" :alt="alternativeText">
    <p v-if="isDisabled" class="unavailable">Indisponible</p>
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
    isDisabled: {
      type: Boolean,
      default: false,
      required: false
    }
  },

  methods: {
    handleClick() {
      /* eslint-disable */
      console.log(this.redirectionLink)
      window.location.href = this.redirectionLink
    }
  }
}
</script>

<style scoped>
img {
  transition: filter .3s;
}
.game {
  cursor: pointer;
  flex: 1;
  margin: 1rem;
  position: relative;
  box-shadow: 0.1em 0.1em .8em rgba(0, 0, 0, 0.9);
  transition: transform .3s;
  border-radius: 4px;
  overflow: hidden;
  max-width: 300px;
}
.game:hover {
  box-shadow: .1em .1em 1em -0.3em rgba(0, 0, 0);
  transform: scale(1.05)
}
.disabled {
  cursor: not-allowed;
}
.disabled img:hover {
  filter: opacity(.1);
}

.unavailable {
  pointer-events: none;
  position: absolute;
  left: 0;
  right: 0;
  top: calc(50%);
  margin: auto;
  -webkit-transform: rotate(-22deg);
  transform: rotate(-14deg) translate(-18%, 0);
  background: linear-gradient(45deg, #212020, #00000096);
  width: 150%;
  padding: 1em;
  font-weight: 700;
  color: #f33f31;
}

img {
  height: 100%;
  width: 100%;
}
</style>