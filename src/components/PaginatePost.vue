<script setup>
defineProps({
    "inicio": Number,
    "posts": Array,
    "postXpage": Number
})


</script>

<template>
    <div class="btn-wrapper">
        <button class="btn" @click="$emit('previus')" :disabled="inicio === 0">Next'nt</button>
        <button class="btn" @click="$emit('next')" :disabled="inicio >= posts.length - postXpage">Next</button>
        
        
    </div>
</template>

<style lang="scss" scoped>

.btn {
    margin: .5rem;
    padding: .5rem 2rem;
    color: black;
    background-color: transparent;
    border: 1px solid gray;
    font-family: sans-serif;
    font-size: 1rem;
    font-weight: bold;
    transition: .3s;
    &:hover {
        color: white;
        background-color: rgb(58, 58, 206);
    }

    &:disabled {
        opacity: .5;
    }
}
</style>