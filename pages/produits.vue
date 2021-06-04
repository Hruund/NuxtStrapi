<template>
    <div class="container">
    <div>
      <div class="bg-gray-200 rounded ring-4 mb-5 ring-gray-400 p-5">
        Découvrez notre séléction de jantes
      </div>
      <div class="text-left">
        <div v-for="products in items" :key="products">
          <div class="flex items-center mb-2 rounded bg-blue-800 text-white">
            <div class="bg-gray-200 rounded overflow-hidden w-20 flex-none border-grey-300 border-t-2 border-b-2">
              <img :src=" 'http://localhost:1337'+products.image.formats.thumbnail.url">
            </div>
            <div class="text-white items-center font-bold ml-4">
              {{ products.Titre }}
            </div>
            <div class="text-white items-center font-bold ml-4">
              {{ products.Price }}€
            </div>
            <div class="text-white items-center font-bold ml-4">
              {{ products.Taille }}""
            </div>
            <div class="text-white items-center font-bold ml-4">
              {{ products.Couleur}}
            </div>
            <div class="text-red-500 font-bold ml-4 text-right ">
              <button v-on:click="$destroyed">X</button>
            </div>
          </div>
        </div>
        <div class="mt-10 "> 
        <NuxtLink to="/produits"><ButtonNavbar insider="Ajouter un produit"/></NuxtLink>
        <NuxtLink to="/produits"><ButtonNavbar insider="Modifier un produit"/></NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: []
    }
  },
  mounted () {
    this.$axios.$get('products').then((response) => {
      this.items = response
    })
  },
  destroyed () {
    this.$axios.delete('anime-shows/'+this.removeId)
  }
}
</script>