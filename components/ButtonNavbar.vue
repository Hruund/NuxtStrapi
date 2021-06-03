<template>
    <button class="bg-transparent mx-5 hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded">
        {{insider}}
    </button>
</template>

<script>
export default {
 props: ['insider']
}
</script>