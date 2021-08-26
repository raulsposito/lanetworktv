<template>
    <main class="lg:relative">
        <div class="mx-auto max-w-7xl w-full pt-16 pb-20 text-center lg:py-48 lg:text-left">
        <div class="px-4 lg:w-1/2 sm:px-8 xl:pr-16">
            <h1 class="text-4xl tracking-tight font-extrabold text-gray-900 sm:text-5xl md:text-6xl lg:text-5xl xl:text-6xl">
            <span class="block xl:inline">Creamos soluciones</span><br />
            <span class="block text-brand xl:inline">Audio Visuales</span>
            </h1>
            <p class="mt-3 max-w-md mx-auto text-lg text-gray-500 sm:text-xl md:mt-5 md:max-w-3xl">
            Nuestra visión, es lograr la fiabilidad y seguridad de los Servicios brindados, basándonos en el trabajo con todos los sistemas operativos mas conocidos (Windows, Mac, Linux).
            </p>
            <p class="mt-3 max-w-md mx-auto text-lg text-gray-500 sm:text-xl md:mt-5 md:max-w-3xl">
            De cada uno lo mejor en rendimiento, calidad, seguridad y confiabilidad, en el prolongado uso de los mismos. Éstos deben resistir el uso diario por parte del cliente para bridarle mejores servicios a su potenciales consumidores o acceso a información inherente a la empresa.
            </p>
        </div>
        </div>
        <div class="relative w-full h-64 sm:h-72 md:h-96 lg:absolute lg:inset-y-0 lg:right-0 lg:w-1/2 lg:h-full">
            <img class="absolute inset-0 w-full h-full object-cover" :src="img" alt="">
        </div>
    </main>
</template>

<script>
export default {
    data() {
        return {
            img: require('../assets/editor.jpg')
        }
    }
}
</script>