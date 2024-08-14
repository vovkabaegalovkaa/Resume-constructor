<template>
    <h4>{{ content }}</h4>
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