<template>
    <img :src="content" alt="Ваша фотография">
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