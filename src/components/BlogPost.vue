<script setup>
defineProps({
    "title": String,
    "id": Number,
    "body": {
        type: String,
        default: "Sin descripcion",
    }
})

</script>

<template>
    <div class="card">
        <div class="card-body">
            <h2 class="card-title">{{id}}- {{ title }}</h2>
            <p class="card-paragraph">
                {{body}}
            </p>

            <button @click="$emit('Cambiar', title)" class="btn">Favorito</button>

        </div>
    </div>
</template>

<style lang="scss">
* {
    font-family: sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

.card {
    width: 100%;
    padding: 1rem;
    border: 1px solid lightgray;
    &-body{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        gap: 2rem;
    }
}
.btn {
    width: max-content;
    background-color: transparent;
    font-size: 1rem;
    padding: .5rem 2rem;
    border-radius: .5rem;
    color: blue;
    border-radius: 1px solid lightblue;
    transition: .3s;
    cursor: pointer;
    
    &:hover {
        background-color: blue;
        color: white;
    }
}
</style>