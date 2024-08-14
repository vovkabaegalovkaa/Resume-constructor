<template>
    <h2>{{ content }}</h2>
</template>

<script>
export default {
    props: {
        content: {
            type: String,
            required: true,
            default: " "
        }
    }
}
</script>