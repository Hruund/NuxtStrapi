<template>

    <div class="mx-52 m-auto my-5">
      <div>
        <h1 class="allProductsTitle">
          Tous nos produits
        </h1>
      </div>
    <div class="border-gray-800">
      <div v-for="product in items" :key="product" class="group shadow-lg hover:bg-white hover:shadow-lg hover:border-transparent bg-gray-100 rounded-full my-4">
        <div class="max-w-7xl max-h-20 mx-auto py-3 px-3 sm:px-6 lg:px-8">
          <div class="flex items-center justify-between flex-wrap">
            <div class="w-0 flex-1 flex items-center">

              <img class=" flex p-2 shadowobject-cover h-12 rounded-full border border-gray-100" :src=" 'http://localhost:1337'+product.image.formats.thumbnail.url">

              <div class="text-gray-800 items-center font-bold ml-4">
                {{ product.name }} // 
              </div>
              <div class="text-gray-800 items-center ml-4">
                <p class="font-bold"> Taille: </p> 
              </div>
              <div class="text-gray-800 items-center ml-4">
                <p>{{ product.size }}""</p>
              </div>
              <div class="text-gray-800 items-center ml-4">
                <p class="font-bold"> Couleur: </p> 
              </div>
              <div class="text-gray-800 items-center ml-4">
                {{ product.Couleur}}
              </div>
            </div>
            <div class="order-3 mt-2 flex-shrink-0 w-full sm:order-2 sm:mt-0 sm:w-auto">
              {{ product.price }} €
            </div>
            <div class="order-2 flex-shrink-0 sm:order-3 sm:ml-3">
              <button @click="deleteProduct(product.id)" type="button" class="-mr-1 font-bold text-gray-900 hover:text-gray-100 flex p-2 rounded-md hover:bg-indigo-500 focus:outline-none focus:ring-2 focus:ring-white sm:-mr-2">
                X
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="flex text-left mt-10">
        <NuxtLink to="/addproduct"><BlankButton insider="Ajouter un produit"/></NuxtLink>
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
  methods:
  {
    loadProduct()
    {
      this.$axios.$get('products').then((response) => {
        this.items = response;
      })
    },
    deleteProduct(id)
    {
      this.$axios.$delete('products/'+id).then((response) => {
        this.items = response;
      })
    }
  },
  destroyed () {
    //
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