<script setup>

const { data: bars } = await useAsyncData(
    "bars",
    async () => {
        const items = await $fetch("https://api.brest.bar/items/bars?fields=id,name,address,category.bars_categories_id.*,type.bars_types_id.*&limit=5")

        console.log(items.data)
        return items.data;
    }
)
</script>

<template>
    <div >
        <div class="flex justifyBetween pad16">
            <h2 class="white-text">Explorer</h2>

            <button class="filter-button white-text pointer">
                Filtrer ✍️
            </button>
        </div>

        <div class="list flex column gap20" v-if="bars">

            <BarCard v-for="bar in bars" :key="bar.id" :info="bar" />

        </div>

        <div class="centered">
            <button class="more-button white-text pointer">Plus</button>
        </div>
    </div>
</template>

<style scoped>
h2 {
    font-size: 2.4rem;
}
.filter-button {
    font-size: 1.6rem;
    background-image: var(--gradient);
    padding: 8px 16px;
    border-radius: 10px;
}
.list{
    padding: var(--pad-16);
}
.more-button{
    font-size: 1.8rem;
    margin: auto;
    padding: 10px 25px;
    background-color: var(--card-bg-color);
    border-radius: 5px;
    margin-bottom: 20px;
}
</style>