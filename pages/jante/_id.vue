<template>
    <div class="m-auto max-w-md grid mt-8  gap-8 grid-cols-1">
        <div class="flex flex-col ">
            <div class="bg-white shadow-md rounded-3xl p-5">
                <div class="flex flex-col sm:flex-row items-center">
                    <h2 class="font-semibold text-lg mr-auto m-auto">Modifier le produit</h2>
                </div>
                <div class="mt-5">
                    <div class="form" @submit.prevent="edit(jante.id)">
                        <form method="post">
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="mb-3 md:space-y-2 w-full text-xs">
                                    <label class="font-semibold text-gray-600 py-2">Nom de la jante<abbr title="required">*</abbr></label>
                                    <input v-model="jante.name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" id="name">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="w-full flex flex-col mb-3">
                                    <label class="font-semibold text-gray-600 py-2">Taille<abbr title="required">*</abbr></label>
                                    <input v-model="jante.size" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" id="taille">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="w-full flex flex-col mb-3">
                                    <label class="font-semibold text-gray-600 py-2">Couleur<abbr title="required">*</abbr></label>
                                    <input v-model="jante.color" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" id="couleur">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="w-full flex flex-col mb-3">
                                    <label class="font-semibold text-gray-600 py-2">Prix<abbr title="required">*</abbr></label>
                                    <input v-model="jante.price" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" id="prix">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <p class="text-xs text-red-500 text-right my-3">Un champ est obligatoire si, il est suivi d'un
                                asterisk <abbr title="Required field">*</abbr></p>
                            <div class="mt-5 text-right md:space-x-3 md:block flex flex-col-reverse">
                                <NuxtLink to="/jante/"><BlankButton insider="Annuler"/></NuxtLink>
                                <GreenButton insider="Modifier"/>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
      items: [],
      jante: {name: '', size: '', price:'', color:''}
    }
  },
  methods:
  {
    edit(id)
    {
      try{
        this.$axios.$put('products/' +id, this.jante).then((response) => {
            console.log("Produit modifié");
            this.$router.push('/jante/')
        })
      } catch (error)
      {
        this.error = error;
      }
    }
  },
  created() {
    const id = this.$route.params.id
    this.$axios.$get(`products/${id}`).then(
        result => {
            this.jante = result
        }
    )
}
}
</script>