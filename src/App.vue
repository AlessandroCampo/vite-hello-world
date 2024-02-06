

<template>
  <AppTitle :titleText='titleText' />
  <img :src="emojiSrc" alt="" srcset="">
  <AppButtons :emojiSrc="emojiSrc" @update-emoji-src="updateEmojiSrc" />
</template>

<script>
import AppTitle from './components/AppTitle.vue'
import AppButtons from './components/AppButtons.vue'

export default {
  components: {
    AppTitle,
    AppButtons
  },
  data() {
    return {
      titleText: "Wanna be my Valentine?",
      emojiSrc: "../src/assets/pleading-face.svg"
    }
  },
  methods: {
    updateEmojiSrc(newSrc) {
      this.emojiSrc = newSrc;
      this.titleText = "Great, see you at 8PM"
    }

  }
}
</script>

<style>
* {
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}

body {
  background-image: url(../src/assets/4871703.jpg);
  background-size: cover;
}

img {
  width: 250px;
}
</style>
