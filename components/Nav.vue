<template>
    <!-- This example requires Tailwind CSS v2.0+ -->
    <header class="bg-white">
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8" aria-label="Top">
        <div class="w-full py-6 flex items-center justify-between border-b border-indigo-500 lg:border-none">
        <div class="flex items-center">
            <a href="#">
            <span class="sr-only">LaNetworkTv</span>
            <img class="h-10 w-auto" :src="logo" alt="LaNetworkTv Logo">
            </a>
            <div class="hidden ml-10 space-x-8 lg:block">
            <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Solutions">
                Servicios
            </a>

            <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Pricing">
                Portfolio
            </a>

            <a href="http://lanetworktv.ddns.net/" target="_blank" class="text-base font-medium text-black hover:text-indigo-50" key="Docs">
                Blog
            </a>

            <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Company">
                Contacto
            </a>
            </div>
        </div>
        <!-- <div class="ml-10 space-x-4">
            <a href="#" class="inline-block bg-indigo-500 py-2 px-4 border border-transparent rounded-md text-base font-medium text-white hover:bg-opacity-75">Sign in</a>
            <a href="#" class="inline-block bg-white py-2 px-4 border border-transparent rounded-md text-base font-medium text-indigo-600 hover:bg-indigo-50">Sign up</a>
        </div> -->
        </div>
        <div class="py-4 flex flex-wrap justify-center space-x-6 lg:hidden">
        <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Solutions">
            Servicios
        </a>

        <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Pricing">
            Portfolio
        </a>

        <a href="http://lanetworktv.ddns.net/" target="_blank" class="text-base font-medium text-black hover:text-indigo-50" key="Docs">
            Blog
        </a>

        <a href="#" class="text-base font-medium text-black hover:text-indigo-50" key="Company">
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