<template>
    <button class="bg-transparent mx-5 hover:bg-red-500 text-red-500 font-semibold hover:text-white py-2 px-4 border border-red-500 hover:border-transparent rounded">
        {{insider}}
    </button>
</template>

<script>
export default {
 props: ['insider']
}
</script>