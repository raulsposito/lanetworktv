<template>
    <header class="bg-white">
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8" aria-label="Top">
        <div class="w-full py-6 flex items-center justify-between border-b border-brand lg:border-none">
        <div class="flex items-center">
            <a href="/">
            <span class="sr-only">LaNetworkTv</span>
            <img class="h-10 w-auto" :src="logo" alt="LaNetworkTv Logo">
            </a>
            <div class="hidden ml-10 space-x-8 lg:block">
            <a href="/servicios" class="text-base font-medium text-black hover:text-brand" key="servicios">
                Servicios
            </a>

            <a href="/portfolio" class="text-base font-medium text-black hover:text-brand" key="portfolio">
                Portfolio
            </a>

            <a href="http://lanetworktv.ddns.net/" target="_blank" class="text-base font-medium text-black hover:text-brand" key="Docs">
                Blog
            </a>

            <a href="/contact" class="text-base font-medium text-black hover:text-brand" key="contact">
                Contacto
            </a>
            </div>
        </div>
        </div>
        <div class="py-4 flex flex-wrap justify-center space-x-6 lg:hidden">
        <a href="/servicios" class="text-base font-medium text-black hover:text-brand" key="servicios">
            Servicios
        </a>

        <a href="/portfolio" class="text-base font-medium text-black hover:text-brand" key="portfolio">
            Portfolio
        </a>

        <a href="http://lanetworktv.ddns.net/" target="_blank" class="text-base font-medium text-black hover:text-brand" key="Docs">
            Blog
        </a>

        <a href="/contact" class="text-base font-medium text-black hover:text-brand" key="contact">
            Contacto
        </a>
        </div>
    </nav>
    </header>
</template>

<script>
export default {
    data() {
        return {
            logo: require('../assets/ehlogo.png')
        }
    }
}
</script>