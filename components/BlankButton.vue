<template>
    <button class="mb-2 md:mb-0 bg-white px-5 py-2 text-sm shadow-sm font-medium tracking-wider border text-gray-600 rounded-full hover:shadow-lg hover:bg-gray-100">
        {{insider}}
    </button>
</template>

<script>
export default {
 props: ['insider']
}
</script>