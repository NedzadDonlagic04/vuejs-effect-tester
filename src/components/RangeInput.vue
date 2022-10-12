<script>
export default {
    props: {
        min: {
            type: String,
            required: true
        },
        max: {
            type: String,
            required: true
        },
        text: {
            type: String,
            required: true
        }
    },
    methods: {
        updatePos()
        {
            const range = this.max - this.min;
            const value = this.$refs.input.value;
            const percent = Math.round((value - this.min) / range * 100);

            this.$refs.output.style.left = `${percent}%`;
            this.$refs.output.style.transform = `translate(calc(-${percent}%), 80%)`;
            this.$refs.output.innerText = value;
        }   
    }
}
</script>

<template>
    <div class="var-container">
        <label :for="text">{{text}}</label>
        <div class="input-container" :data-min="min" :data-max="max">
            <input @input="updatePos" ref="input" :id="text" type="range" :min="min" :max="max" :value="min">
            <output ref="output" class="range-output" :for="text">{{min}}</output>
        </div>
    </div>
</template>

<style scoped>
    .var-container {
        height: 100%;
        width: 100%;
        color: white;

        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;

        accent-color: var(--yellow-base);
    }

    .var-container label {
        font-size: 1.5rem;
        user-select: none;
    }

    .var-container label::first-letter {
        text-transform: uppercase;
    }

    .input-container {
        display: flex;
        justify-content: center;
        position: relative;
    }

    .input-container::before {
        content: attr(data-min);
        margin: .1rem;
    }

    .input-container::after {
        content: attr(data-max);
        margin: .1rem;
    }

    .range-output {
        user-select: none;
        position: absolute;
        bottom: 0;
        left: 0;
        transform: translateY(80%);
    }

    input[type="range"]:hover {
        cursor: pointer;
    }
</style>