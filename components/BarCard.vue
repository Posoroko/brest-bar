<script setup>
const props = defineProps({
    info: Object,
});
</script>

<template>
    <div class="card">
        
        <div class="topBox flex justifyBetween alignCenter">
            <div class="box">
                <p class="type">{{ info.type[0] ? info.type[0].bars_types_id.name : "pas définie" }}</p>
                <h2 class="white-text">{{ info.name }}</h2>
                <p class="address">🏃‍♂️ {{ info.address }}</p>
            </div>

            <button class="centered">
                👁️
            </button>
        </div>

        <div class="tagBox flex gap10">
            <div class="tag white-text" v-for="cat in info.category" :key="cat.bars_categories_id.id">
                {{ cat.bars_categories_id.name }}
            </div>
        </div>
    </div>
</template>

<style scoped>
.card {
    background-color: var(--card-bg-color);
    padding: var(--pad-16);
    border-radius: 15px;
    
}
.type {
        font-size: 1.6rem;
        font-weight: 700;
        text-transform: uppercase;
        color: var(--purple);
    }
h2 {
    font-size: 2.4rem;
}
.address {
    font-size: 1.6rem;
    color: #b066f3;
}
button {
    background-color: var(--purple);
    padding: 16px;
    border-radius: 500px;
}
.tag {
    font-size: 1.6rem;
    color: #3d64d1;
    background-color: rgba(61,100,209,.3);
    padding: 5px 10px;
    border-radius: 50px;
    margin-top: 10px;
}
</style>