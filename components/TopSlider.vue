<template>
  <main>
    <div>
      <div>
        <div class="h-auto">
            <carousel
                ref="Carousel"
                :per-page="1"
                :mouse-drag="false"
                :pagination-enabled="false"
                :navigation-enabled="false"
                :autoplay="true"
                :loop="true"
                :speed="2000"
                :autoplay-timeout="5000"
            >
                <slide
                v-for="(image, index) in images"
                :key="image.index"
                :index="index"
                class="h-full"
                >
                <div
                    id="me"
                    class="relative h-96 bg-gray-300 mix-blend-multiply"
                >
                    <div class="relative inset-0 z-10">
                        <div class="relative max-w-7xl mx-auto py-24 px-4 sm:py-32 sm:px-6 lg:px-8">
                            <h1 class="text-4xl font-extrabold tracking-tight text-white sm:text-5xl lg:text-6xl">{{ image.text }}</h1>
                            <p class="mt-6 text-xl text-indigo-100 max-w-3xl">{{ image.undertext }}</p>
                        </div>
                    </div>
                    <div class="absolute inset-0 z-5">
                    <img
                        class="h-full min-w-full object-cover"
                        :src="image.url"
                    />
                    </div>
                </div>
                </slide>
            </carousel>
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import { Carousel, Slide } from 'vue-carousel'
export default {
  components: {
        Carousel,
        Slide,
    },
    data() {
        return {
            images: [
                {
                    index: 0,
                    url: require('../assets/slider1.png'),
                    text: 'Donde el arte se junta con la tecnología',
                    undertext: 'Efectos visuales y creativos',
                },
                {
                    index: 1,
                    url: require('../assets/slider2.png'),
                    text: 'Ideas transformadas en realidad',
                    undertext: 'Soluciones Audio Visuales',
                },
                {
                    index: 2,
                    url: require('../assets/slider3.png'),
                    text: 'Fusión de pasión y profesionalismo',
                    undertext: 'Desarrollos creativos y funcionales',
                },
            ]
        }
    },
    methods: {
        nextSlide() {
        this.$refs.Carousel.goToPage(
            this.$refs.Carousel.getNextPage(),
            (this.$refs.scrollLBtn.disabled = false)
        )
        if (this.$refs.Carousel.canAdvanceBackward === false)
            this.$refs.scrollLBtn.disabled = true
        if (this.$refs.Carousel.canAdvanceForward === false)
            this.$refs.scrollRBtn.disabled = true
        },
        prevSlide() {
        this.$refs.Carousel.goToPage(
            this.$refs.Carousel.getPreviousPage(),
            (this.$refs.scrollRBtn.disabled = false)
        )
        if (this.$refs.Carousel.canAdvanceForward === false)
            this.$refs.scrollRBtn.disabled = true
        if (this.$refs.Carousel.canAdvanceBackward === false)
            this.$refs.scrollLBtn.disabled = true
        },
    },
}
</script>