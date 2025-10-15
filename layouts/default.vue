<template>
    <header class = "flex flex-row w-full bg-black text-black max-sm:justify-between max-sm:relative">
        <div class = "basis-1/4 items-center justify-start px-4 py-2 max-sm:basis-auto">
            <img src="assets/images/download.png" class="w-16 h-16 rounded-3xl bg-transparent">
        </div> 
        <div class = "basis-1/4 max-sm:basis-auto">
        </div>
        <nav :class="{'basis-1/2 flex flex-row items-center bg-gradient-to-r from-blue-600 via-green-500 to-indigo-400 text-transparent bg-clip-text justify-end px-8 gap-4': !burger || burger,
         'max-sm:basis-auto max-sm:absolute max-sm:top-full max-sm:w-full max-sm:justify-center max-sm:flex-col max-sm:gap-0 max-sm:bg-gradient-to-r from-purple-950 via-indigo-700 to-pink-400 max-sm:px-0': burger,'max-sm:hidden':!burger}">
      <NuxtLink to="/" class="my-auto p-2 hover:bg-blue-700 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center">Home</NuxtLink>
      <div class="my-auto p-2 hover:bg-yellow-300 hover:text-white max-sm:w-full max-sm:text-center max-sm:px-0 max-sm:pb-0" @click = "switch_submenu">Labs
        <div class="flex flex-col absolute bg-gradient-to-r from-blue-950 via-blue-700 to-blue-300  text-black w-56 text-center max-sm:relative max-sm:w-full max-sm:bg-red-100" v-show = "submenu">
          <NuxtLink to="/lab3" class="my-auto p-2 border-b-2 border-black hover:bg-gradient-to-r from-black via-gray-500 to-white hover:text-white max-sm:w-full max-sm:border-t-2 max-sm:text-center">Lab3</NuxtLink>
          <NuxtLink to="/lab4" class="my-auto p-2 border-b-2 border-black hover:bg-gradient-to-r from-black via-gray-500 to-white hover:text-white max-sm:w-full max-sm:text-center">Lab4</NuxtLink>
          <NuxtLink to="/lab5" class="my-auto p-2 border-b-2 border-black hover:bg-gradient-to-r from-black via-gray-500 to-white hover:text-white max-sm:w-full max-sm:text-center">Lab5</NuxtLink>
          <NuxtLink to="/lab6" class="my-auto p-2 border-b-2 border-black hover:bg-gradient-to-r from-black via-gray-500 to-white hover:text-white max-sm:w-full max-sm:border-black max-sm:text-center">Lab6</NuxtLink>
        </div>
      </div>
      <NuxtLink to="/login" :class="{'my-auto p-2 hover:bg-pink-800 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center': submenu,
      'my-auto p-2 hover:bg-orange-400 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-t-2 max-sm:border-black max-sm:text-center': !submenu}">LogIn</NuxtLink>
      <NuxtLink to="/logout" class="my-auto p-2 hover:bg-green-900 hover:text-white max-sm:w-full max-sm:border-b-2 max-sm:border-black max-sm:text-center">LogOut</NuxtLink>
        </nav>
        <div v-if ="!burger" @click ="switch_burger" class = "max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6">
      <span class="h-[3px] w-full bg-blue-950"></span>
      <span class="h-[3px] w-full bg-blue-950"></span>
      <span class="h-[3px] w-full bg-blue-950"></span>
    </div>
    <div v-else class = "max-sm:flex max-sm:flex-col max-sm:mr-8 max-sm:justify-between max-sm:items-center max-sm:w-8 max-sm:h-6" @click="switch_burger">
      <span class="h-[3px] w-full bg-blue-950 rotate-45 relative top-[9px]"></span>
      <span class="h-[3px] w-full bg-blue-950 opacity-0"></span>
      <span class="h-[3px] w-full bg-blue-950 relative bottom-3 rotate-[-45deg]"></span>
    </div>
    </header>
    
    
    <main class="p-5 flex bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 h-screen ">
        <slot />     
    </main>
    <footer class = "flex flex-row w-full bg-black border-t-2 border-gray-400 items-center justify-center px-4 py-2 gap-4">
        <a href = "https://www.youtube.com/"><img src="assets/images/youtube.png" class = "w-16 h-16 rounded-full"></a>
        <a href = "https://github.com/"><img src="assets/images/githube.png" class = "w-16 h-16 rounded-full"></a>
        <a href = "https://www.facebook.com/"><img src="assets/images/facebook.png" class = "w-16 h-16 rounded-full"></a>
    </footer>
</template>

<script setup lang="ts">
import { useHead } from '#app';
import {ref} from 'vue'

useHead({
    script: [
    {
        async: true,
        src:'https://www.googletagmanager.com/gtag/js?id=G-C86QR55W5D',
    },
        {
            innerHTML: `
            window.dataLayer = window.dataLayer || [];
            function gtag(){dataLayer.push(arguments);}
            gtag('js', new Date());
            gtag('config', 'G-C86QR55W5D');
            `,
            type: 'text/javascript',
        },
    ],
    __dangerouslyDisableSanitizersByTagID: {
        gtag: ['innerHTML'],
    },
});
const burger = ref<boolean>(false)
const submenu = ref<boolean>(false)

const switch_burger = ()=> {burger.value = !burger.value}
const switch_submenu = ()=> {submenu.value = !submenu.value}

</script>
   <!-- <flamingo>
    +77078424363
   </flamingo> -->

   