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

              <img v-if="product.image" class=" flex p-2 shadowobject-cover h-12 rounded-full border border-gray-100" :src=" 'http://localhost:1337'+product.image.formats.thumbnail.url">
              <img v-else class=" flex p-2 shadowobject-cover h-12 rounded-full border border-gray-100" src="../../img/no_image.jpg" alt="">

              <div class="text-gray-800 items-center font-bold ml-4">
                {{ product.name }} |
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
            <div class="order-3 mt-2 flex-shrink-0 w-full sm:order-2 sm:mt-0 sm:w-auto">
              <button  @click="getItem(product.id)" class="mx-5 hover:text-gray-100 hover:bg-blue-300 text-gray-900 font-semibold py-2 px-4 rounded-full shadow">
                Modifier
              </button>
            </div>
            <div class="order-2 flex-shrink-0 sm:order-3 sm:ml-3">
              <button @click="deleteProduct(product.id)" type="button" class="rounded-full hover:bg-blue-300 text-gray-900 hover:rounded-full text-red-500 -mr-1 font-bold hover:text-gray-100 flex p-2 sm:-mr-2">
                X
              </button>
            </div>
          </div>
        </div>
      </div>
      <div class="flex text-left mt-10">
        <NuxtLink to="/jante/add"><BlankButton insider="Ajouter un produit"/></NuxtLink>
        <NuxtLink to="/jante/products"><BlankButton @click="loadProduct()" insider="Rafraichir"/></NuxtLink>
      </div>
      <div class="flex text-left mt-10">
        
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
        //loadProduct();
      })
    },
    getItem(id) {
      this.$router.push(`products/${id}`)
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