<script>
export default {
    props: {
        blur: {
            type: String,
            required: true
        },
        space: {
            type: String,
            required: true
        },
        color: {
            type: String,
            required: true
        }
    }
}
</script>

<template>
    <div class="img-container" :style="{ backgroundColor: color, padding: 1/2*space + 'rem ' + space + 'rem', filter: `blur(${blur}px)`}">
        <img src="./../assets/img/hike.jpeg" alt="person hiking">
    </div>
</template>

<style scoped>
    img {
        max-width: 100%;
        max-height: 100%;
    }

    .img-container {
        background-color: black;
        user-select: none;
        height: 31rem;
        grid-row: 3/4;
        grid-column: 1/4;
        margin: auto;
    }
</style>