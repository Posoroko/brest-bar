<template>
    <header class="flex justifyBetween alignCenter">
        <p class="white-text">🍻 Brest <span class="gradient-text"> bar</span></p>

        <button class="request white-text pointer">
            <span>🙋‍♀️ </span>
            <span>Faire une demande</span>
        </button>
    </header>
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

</style>