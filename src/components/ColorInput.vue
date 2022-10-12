<script>
export default {
    props: {
        text: {
            type: String,
            required: true
        }
    },
    emits: ['change'],
    methods: {
        updateColor(event)
        {
            this.$emit('change', event.target.value);
        }
    }
}
</script>

<template>
    <div class="var-container">
        <label for="color">{{text}}</label>
        <input @input="updateColor" type="color">
    </div>
</template>

<style scoped>
    .var-container {
        height: 100%;
        width: 100%;
        color: white;
        user-select: none;

        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        accent-color: var(--yellow-base);
    }

    .var-container label {
        font-size: 1.5rem;
    }

    .var-container label::first-letter {
        text-transform: uppercase;
    }

    input[type="color"]:hover {
        cursor: pointer;
    }
</style>