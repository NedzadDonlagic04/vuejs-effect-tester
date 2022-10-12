<script>
import RangeInput from './components/RangeInput.vue';
import Image from './components/Image.vue';

export default {
    components: {
        RangeInput,
        Image
    }
}
</script>

<template>
    <h1>Update CSS Variables with <span class="yellow-txt">JS</span></h1>
    <RangeInput />
    <Image />
</template>

<style scoped>
    h1 {
        font-size: 3rem;
        text-align: center;
        margin: auto;
        color: white;
        grid-column: 1/4;
        user-select: none;
    }

    .yellow-txt {
        color: hsl(44, 100%, 50%);
    }
</style>