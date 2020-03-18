<template>
    <div>
        <p>{{ quote }}</p>
    </div>
</template>

<script>
    export default {
        props: {
            quote: {
                type: String,
                required: true,
            },
        },
    }
</script>

<style scoped>

</style>