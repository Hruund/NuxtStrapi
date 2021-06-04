<template>
    <button class="bg-green-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full" type="submit">
        {{insider}}
    </button>
</template>

<script>
export default {
 props: ['insider']
}
</script>