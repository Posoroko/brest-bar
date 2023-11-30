<script setup>
const isModalOpen = ref(false);

</script>



<template>
    <header class="flex justifyBetween alignCenter">
        <p class="white-text">🍻 Brest <span class="gradient-text"> bar</span></p>

        <button class="request white-text pointer" @click="isModalOpen = true">
            <span>🙋‍♀️ </span>
            <span>Faire une demande</span>
        </button>
    </header>

    <dialog class="flex alignCenter justifyCenter gap10" v-if="isModalOpen">
        <p class="demande">Demande</p>
        <button class="close-btn flex justifyCenter alignCenter pointer" @click="isModalOpen = false">
            
            <svg xmlns="http://www.w3.org/2000/svg" height="24" viewBox="0 -960 960 960" width="24"><path d="m256-200-56-56 224-224-224-224 56-56 224 224 224-224 56 56-224 224 224 224-56 56-224-224-224 224Z"/></svg>
            
        </button>
    </dialog>
</template>

<style scoped>
header {
    padding: 0 1.6rem;
    height: 70px;
    box-shadow: 0 0 1rem rgba(0, 0, 0, 0.2);
}
p {
    font-size: 2.8rem;
    
    span {
        font-weight: 400;
    }
}

.request {
    font-size: 1.4rem;
    font-weight: 700;
    background-color: var(--purple);
    padding: 10px 20px;
    border-radius: 5px;
}
dialog {
    padding: 20px;
    border: none;
    border-radius: 10px;
    background-color: #201f23;
    border: 1px solid var(--card-bg-color);
    box-shadow: 1px 1px 10px rgba(0, 0, 0, 0.596);
    top:50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.close-btn {
    background-color: var(--card-bg-color);
    fill: white;
    width: 40px;
    height: 40px;
    border-radius: 10px;
}
.demande {
    color: white;
    font-size: 2.6rem;
    font-weight: 700;
    line-height: 1em;
    margin-left: 10px;
}
</style>