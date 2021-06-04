<template>
    <button class="mx-5 hover:text-gray-100 hover:bg-blue-300 text-gray-900 font-semibold py-2 px-4 rounded-full shadow">
        {{insider}}
    </button>
</template>

<script>
export default {
 props: ['insider']
}
</script>