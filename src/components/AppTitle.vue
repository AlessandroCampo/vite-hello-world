<script>
export default {
    props: ['titleText'],
}
</script>

<template>
    <h1 ref="title"> {{ titleText }}</h1>
</template>

<style scoped>
h1 {
    color: red
}
</style>