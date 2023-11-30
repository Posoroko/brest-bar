<script setup>
const buttons= [
    {id: "1",emoji: "🍷", name: "Cave"},
    {id: "2",emoji: "🍺", name: "Brasserie" },
    {id: "3",emoji: "🍹", name: "Bar" }
];
const activeBtn = ref("Cave");

</script>

<template>
    <div class="ou-boire-box border-bottom">
        <h2 class="white-text">
            Ou boire à Brest ?
        </h2>

        <div class="filter-box flex justifyEvenly">
            <button class="button-box pointer flex column alignCenter gap10" 
                v-for="btn in buttons" 
                :key="btn.id"
                @click="activeBtn = btn.name"
                >
                <div class="button centered">{{ btn.emoji }}</div>
            
                <p class="white-text centered" :class="{ 'active': activeBtn == btn.name }">{{ btn.name }}</p>
            </button>
        </div>
    </div>
</template>

<style scoped>
.ou-boire-box {
    padding-bottom: 1.6rem;
}

h2 {
    font-size: 2.4rem;
    padding: 1.6rem;
}

button {
    width: 30%;
    background-color: transparent;
}
.button {
    width: 100%;
    aspect-ratio: 1/1;
    font-size: 3.6rem;
    background-color: var(--card-bg-color);
    border-radius: 10px;
    border: none;
}

p {
    font-size: 1.6rem;    
}
p.active {
    color: var(--purple);
}
</style>