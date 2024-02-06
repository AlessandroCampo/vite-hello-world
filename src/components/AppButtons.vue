<script>
export default {
    props: ['emojiSrc'],
    methods: {
        randomizePosition() {
            const noButton = this.$refs.no
            gsap.to(noButton, {
                top: this.generateRandomPosition(),
                left: this.generateRandomPosition(),
                duration: 0.1
            })
        },
        generateRandomPosition() {
            const randomCoord = Math.floor(Math.random() * 90)
            return (randomCoord + "%")
        },
        changeTitleEmoji() {
            console.log("Clicked, emojiSrc:", this.emojiSrc);
            this.$emit('update-emoji-src', "../src/assets/drunk-with-love.png");
        },
    }
}

</script>

<template>
    <button class="yes" ref="yes" @click="changeTitleEmoji">
        Yes
    </button>
    <button class="no" ref="no" @mouseenter="randomizePosition">
        No
    </button>
</template>

<style scoped>
h1 {
    color: red;
}

button {
    font-size: 35px;
    border: 1px solid red;
    color: red;
    background-color: lightpink;
    border-radius: 50px;
    width: 150px;
    text-align: center;
}

button {
    cursor: pointer;
    position: absolute;
}

button.yes {
    left: 40%;
    top: 80%;
}

button.no {
    right: 40%;
    top: 80%;
}
</style>