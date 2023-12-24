<template>
    <div>
        <input type="text" id="id" @change="handleChange">
    </div>
</template>

<script>
export default {
    props: {
        id: String,
    },
    methods: {
        handleChange(event) {
            this.$emit('change', event.target.files[0])
        }
    },
}
</script>