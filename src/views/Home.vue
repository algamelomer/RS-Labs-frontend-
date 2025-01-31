<template>
    <main class="bg-[url('@/assets/images/bg.jpg')] bg-cover bg-center h-full flex flex-col">
        <section style="background-color: rgba(0, 0, 0, 0.35);" class=" w-fit h-fit mt-20 sm:ml-7 p-5 sm:rounded-2xl">
            <p class=" flex flex-col font-normal text-5xl sm:text-6xl md:text-7xl text-white ">
                <span>subtle clinical &</span>
                <span>laboratory test</span>
            </p>
        </section>
        <section class=" h-full my-16 md:my-auto md:h-60 w-full flex md:flex-row flex-col justify-around xl:px-64 py-6 items-center m-auto"
            style="background-color: rgba(0, 0, 0, 0.7);">
            <CustomIconContainer text="Home" :icon="homeIcon" :route="{ name: 'home' }" />
            <CustomIconContainer text="Doctor" :icon="DoctorIcon" :route="{ name: 'home' }" />
            <CustomIconContainer text="Patient" :icon="PatientIcon" :route="{ name: 'home' }" />
            <CustomIconContainer text="Labs" :icon="LabToLabIcon" :route="{ name: 'home' }" />
        </section>
    </main>
    <!-- 163 141 30 190 159-->

</template>

<script setup>
import CustomIconContainer from '@/components/CustomIconContainer.vue';
import { ref } from 'vue';

const homeIcon = ref('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><!--!Font Awesome Free 6.7.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2025 Fonticons, Inc.--><path d="M575.8 255.5c0 18-15 32.1-32 32.1l-32 0 .7 160.2c0 2.7-.2 5.4-.5 8.1l0 16.2c0 22.1-17.9 40-40 40l-16 0c-1.1 0-2.2 0-3.3-.1c-1.4 .1-2.8 .1-4.2 .1L416 512l-24 0c-22.1 0-40-17.9-40-40l0-24 0-64c0-17.7-14.3-32-32-32l-64 0c-17.7 0-32 14.3-32 32l0 64 0 24c0 22.1-17.9 40-40 40l-24 0-31.9 0c-1.5 0-3-.1-4.5-.2c-1.2 .1-2.4 .2-3.6 .2l-16 0c-22.1 0-40-17.9-40-40l0-112c0-.9 0-1.9 .1-2.8l0-69.7-32 0c-18 0-32-14-32-32.1c0-9 3-17 10-24L266.4 8c7-7 15-8 22-8s15 2 21 7L564.8 231.5c8 7 12 15 11 24z"/></svg>');
const DoctorIcon = ref('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--!Font Awesome Free 6.7.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2025 Fonticons, Inc.--><path d="M224 256A128 128 0 1 0 224 0a128 128 0 1 0 0 256zm-96 55.2C54 332.9 0 401.3 0 482.3C0 498.7 13.3 512 29.7 512l388.6 0c16.4 0 29.7-13.3 29.7-29.7c0-81-54-149.4-128-171.1l0 50.8c27.6 7.1 48 32.2 48 62l0 40c0 8.8-7.2 16-16 16l-16 0c-8.8 0-16-7.2-16-16s7.2-16 16-16l0-24c0-17.7-14.3-32-32-32s-32 14.3-32 32l0 24c8.8 0 16 7.2 16 16s-7.2 16-16 16l-16 0c-8.8 0-16-7.2-16-16l0-40c0-29.8 20.4-54.9 48-62l0-57.1c-6-.6-12.1-.9-18.3-.9l-91.4 0c-6.2 0-12.3 .3-18.3 .9l0 65.4c23.1 6.9 40 28.3 40 53.7c0 30.9-25.1 56-56 56s-56-25.1-56-56c0-25.4 16.9-46.8 40-53.7l0-59.1zM144 448a24 24 0 1 0 0-48 24 24 0 1 0 0 48z"/></svg>');
const PatientIcon = ref('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M22.102 11.147v1.731H1.904V6.672H0v12.414h1.904v-2.837h20.198v3.074H24v-8.178z"/><path fill="currentColor" d="M8.709 11.165v.001c0 .564-.457 1.022-1.022 1.022H3.793a1.022 1.022 0 0 1-1.022-1.022v-.002c0-.564.457-1.022 1.022-1.022h3.894c.564 0 1.022.457 1.022 1.022zm11.034-4.001h-2.37V4.8h-1.68v2.365h-2.365v1.68h2.364v2.365h1.68V8.845h2.37z"/></svg>');
const LabToLabIcon = ref('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 512"><!--!Font Awesome Free 6.7.2 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2025 Fonticons, Inc.--><path d="M175 389.4c-9.8 16-15 34.3-15 53.1c-10 3.5-20.8 5.5-32 5.5c-53 0-96-43-96-96L32 64C14.3 64 0 49.7 0 32S14.3 0 32 0L96 0l64 0 64 0c17.7 0 32 14.3 32 32s-14.3 32-32 32l0 245.9-49 79.6zM96 64l0 96 64 0 0-96L96 64zM352 0L480 0l32 0c17.7 0 32 14.3 32 32s-14.3 32-32 32l0 150.9L629.7 406.2c6.7 10.9 10.3 23.5 10.3 36.4c0 38.3-31.1 69.4-69.4 69.4l-309.2 0c-38.3 0-69.4-31.1-69.4-69.4c0-12.8 3.6-25.4 10.3-36.4L320 214.9 320 64c-17.7 0-32-14.3-32-32s14.3-32 32-32l32 0zm32 64l0 160c0 5.9-1.6 11.7-4.7 16.8L330.5 320l171 0-48.8-79.2c-3.1-5-4.7-10.8-4.7-16.8l0-160-64 0z"/></svg>');

</script>