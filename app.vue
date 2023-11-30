<script setup>
let userLocation = ref(null);

const getUserLocation = () => {
    if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(
            (position) => {
                userLocation.value = {
                    lat: position.coords.latitude,
                    lng: position.coords.longitude,
                };
                // console.log(userLocation.value);
            },
            (error) => {
                console.error("Error getting location: ", error);
            }
        );
    } else {
        console.error("Geolocation is not supported by this browser.");
    }
};

getUserLocation();

</script>

<template>
  <div class="siteBox h100vh flex column">
    <TopBar />

    <main class="flex">
        <div class="leftBox flex column ">
  
                <h1 class="intro-text white-text border-bottom">
                    Trouver le bar qu'il vous faut <span class="gradient-text">selon votre humeur</span>
                </h1>

                <OuBoire />

                <div class="blox grow">
                    <ResultsList />
                </div>

        </div>

        <div class="mapBox"></div>
    </main>
  </div>
</template>

<style scoped>
.siteBox {
    overflow: hidden;
}
main {
    height: calc(100vh - 70px);

}
.leftBox {
    width: 33.333333%;
    height: 100%;
    overflow: scroll;
}
@media screen and (max-width: 1022px) {
    .leftBox {
        width: 80%;
    }
    
}

.intro-text {
    font-size: 3.6rem;
    font-weight: 700;
    line-height: 4rem;
    padding: 1.6rem;
    
}
</style>