<script>
import RangeInput from './components/RangeInput.vue';
import Image from './components/Image.vue';
import ColorInput from './components/ColorInput.vue'

export default {
    components: {
        RangeInput,
        Image,
        ColorInput
    },
    data()
    {
        return {
            blur: '0',
            space: '0',
            color: '0x000000'
        }
    },
    methods: {
        blurHandle(value) 
        {
            this.blur = value;
        },
        spaceHandle(value)
        {
            this.space = value;
        },
        colorHandle(value)
        {
            this.color = value;
        }
    }
}
</script>

<template>
    <h1>Update CSS Variables with <span class="yellow-txt">JS</span></h1>
    <RangeInput min="0" max="10" text="blur" @change="blurHandle"/>
    <RangeInput min="0" max="10" text="space" @change="spaceHandle"/>
    <ColorInput text="color" @change="colorHandle"/>
    <Image :blur="blur" :space="space" :color="color"/>
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