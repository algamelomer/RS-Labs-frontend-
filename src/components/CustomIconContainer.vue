<template>
    <router-link :to="route">
        <main class="flex flex-col items-center">
            <div
                :class="`flex items-center justify-center w-40 h-36 bg-white rounded-4xl cursor-pointer transform duration-500 ease-in-out hover:bg-custom-red hover:w-48 hover:h-40 ${customClass}`">
                <!-- Use v-html for inline SVG or img for regular images -->
                <div v-if="isSvg" v-html="icon" class="w-4/6 icon-style"></div>
                <img v-else :src="icon" :alt="text" class="w-4/6 object-cover icon-style" />
            </div>
            <p class="mt-2 text-center text-white text-md font-bold">{{ text }}</p>
        </main>
    </router-link>
</template>

<script setup>
import { computed } from 'vue';

const props = defineProps({
    text: {
        type: String,
        required: true,
    },
    icon: {
        type: String,
        required: true,
    },
    route: {
        type: [String, Object],
        required: true,
    },
    customClass: {
        type: String,
        default: '',
    },
});

// Check if the icon is an SVG (inline) or an image (src)
const isSvg = computed(() => {
    return props.icon.startsWith('<svg'); // Check if the icon string starts with <svg
});
</script>

<style scoped>
/* Style for icons */
.icon-style {

    filter: brightness(0) saturate(100%) invert(32%) sepia(73%) saturate(2337%) hue-rotate(334deg) brightness(101%) contrast(82%);
    transition: filter 0.3s ease-in-out;
}

.hover\:bg-custom-red:hover .icon-style {
    filter: brightness(0) invert(1);
}
</style>