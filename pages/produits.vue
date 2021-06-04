<template>

    <div class="mx-52 m-auto my-5">
      <div>
        <h1 class="allProductsTitle">
          Tous nos produits
        </h1>
      </div>
    <div class="border-gray-800">
      <div v-for="products in items" :key="products" class="group shadow-lg hover:bg-white hover:shadow-lg hover:border-transparent bg-gray-100 rounded-full my-4">
        <div class="max-w-7xl max-h-20 mx-auto py-3 px-3 sm:px-6 lg:px-8">
          <div class="flex items-center justify-between flex-wrap">
            <div class="w-0 flex-1 flex items-center">

                <img class=" flex p-2 shadowobject-cover h-12 rounded-full border border-gray-100" :src=" 'http://localhost:1337'+products.image.formats.thumbnail.url">

              <div class="text-gray-800 items-center font-bold ml-4">
                {{ products.Titre }}
              </div>
              <div class="text-gray-800 items-center font-bold ml-4">
                {{ products.Taille }}""
              </div>
              <div class="text-gray-800 items-center font-bold ml-4">
                {{ products.Couleur}}
              </div>
            </div>
            <div class="order-3 mt-2 flex-shrink-0 w-full sm:order-2 sm:mt-0 sm:w-auto">
              {{ products.Price }} €
            </div>
            <div class="order-2 flex-shrink-0 sm:order-3 sm:ml-3">
              <button @click="deleteProduct(product.id)" v-on:click="$destroyed" type="button" class="-mr-1 flex p-2 rounded-md hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-white sm:-mr-2">
                <p>X</p>
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="flex text-left mt-10">
        <NuxtLink to="/produits"><BlankButton insider="Ajouter un produit"/></NuxtLink>
        <NuxtLink to="/produits"><BlankButton insider="Modifier un produit"/></NuxtLink>
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
      this.items = response;
    })
  },
  method:
  {
    loadCart()
    {
      this.$axios.$get('products').then((response) => {
        this.items = response;
      })
    },
    deleteProduct(id)
    {
      this.$axios.$delete('product/'+id).then((response) => {
        this.items = response;
      })
    }
  },
  destroyed () {
    this.$axios.delete('anime-shows/'+this.removeId);
  }
}
</script>

<style>
.allProductsTitle {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 30px;
  color: #35495e;
  letter-spacing: 1px;
}
</style>