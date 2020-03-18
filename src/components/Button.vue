<template>
    <div id="kanye-button" @click='notifyParentUpdateQuote'>
        <p >Click me for more Kanye!</p>
    </div>
</template>

<script>
    export default {
        methods: {
            notifyParentUpdateQuote: function() {
                this.$emit('updateQuote')
            }
        }
    }
</script>

<style scoped>

</style>