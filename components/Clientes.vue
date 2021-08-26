<template>
    <ul role="list" class="grid grid-cols-1 pb-16 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4">
    <div v-for="(client, index) in clients" :key="client.name" :index="index">
        <li class="col-span-1 flex flex-col text-center bg-white rounded-lg shadow divide-y divide-gray-200">
            <div class="flex-1 flex flex-col p-8">
            <img class="w-32 h-32 object-contain flex-shrink-0 mx-auto rounded-full" :src="client.img" alt="">
            <h3 class="mt-6 text-gray-900 text-sm font-medium">{{ client.name }}</h3>
            <dl class="mt-1 flex-grow flex flex-col justify-between">
                <dt class="sr-only">Title</dt>
                <dd v-if="client.text" class="text-gray-500 text-sm">{{ client.text }}</dd>
                <dt class="sr-only">Role</dt>
                <div class="mt-3">
                <a :href="client.link" target="blank" class="px-2 py-1 text-green-800 text-xs font-medium bg-green-100 rounded-full">{{ client.name }}</a>
                </div>
            </dl>
            </div>
        </li>
    </div>

    <!-- More people... -->
    </ul>
</template>

<script>
export default {
    data() {
        return {
            clients: [
                {
                    img: require('../assets/1montecarlo.png'),
                    name: "Monte Carlo",
                    link: "http://www.montecarlotv.com.uy/",
                    text: "Monte Carlo TV es un canal de televisión abierta uruguayo. Es la segunda emisora más antigua del país.",
                },
                {
                    img: require('../assets/2canalsiete.png'),
                    name: "Canal Siete",
                    link: "http://www.canal7.com.uy/",
                    text: "Canal Siete es un canal de televisión abierta uruguayo.",
                },
                {
                    img: require('../assets/3rtve.png'),
                    name: "rtve",
                    link: "https://www.rtve.es/",
                    text: "Canal RTVE TV Libre",
                },
                {
                    img: require('../assets/4solis.png'),
                    name: "Teatro Solís",
                    link: "https://www.teatrosolis.org.uy/home",
                    text: "El Teatro Solís constituye el principal escenario artístico de la ciudad de Montevideo.",
                },
                {
                    img: require('../assets/5wlounge.png'),
                    name: "W Lounge",
                    link: "--",
                    text: "W Lounge",
                },
                {
                    img: require('../assets/6cerrolargo.png'),
                    name: "Intendencia de Cerro Largo",
                    link: "--",
                    text: "Gobierno de Cerro Largo, Ciudad De Melo, Uruguay.",
                },
                {
                    img: require('../assets/7audepp.png'),
                    name: "AUDEPP",
                    link: "http://www.audepp.org/portal/",
                    text: "AUDEPP Asociación Uruguaya de Psicoterapia Psicoanalítica.",
                },
                {
                    img: 'https://st2.depositphotos.com/4060975/8056/v/600/depositphotos_80565530-stock-illustration-plus-vector-icon.jpg',
                    name: "Ser el proximo!",
                    link: "/contact",
                }
            ]
        }
    }
}
</script>