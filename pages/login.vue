<template>
    <div class="m-auto max-w-md grid mt-8  gap-8 grid-cols-1">
        <div class="flex flex-col ">
            <div class="bg-white shadow-md rounded-3xl p-5">
                <div class="flex flex-col sm:flex-row items-center">
                    <h2 class="font-semibold text-lg mr-auto m-auto">Connexion</h2>
                </div>
                <div class="mt-5">
                    <div class="form">
                        <form method="post" @submit.prevent="login">
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="mb-3 md:space-y-2 w-full text-xs">
                                    <label class="font-semibold text-gray-600 py-2">Adresse email<abbr title="required">*</abbr></label>
                                    <input v-model="email" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="email" id="email">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                                <div class="w-full flex flex-col mb-3">
                                    <label class="font-semibold text-gray-600 py-2">Mot de passe<abbr title="required">*</abbr></label>
                                    <input v-model="password" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="password" id="password">
                                    <p class="text-red text-xs hidden">Veuillez remplir ce champ.</p>
                                </div>
                            </div>
                            <p class="text-xs text-red-500 text-right my-3">Un champ est obligatoire si, il est suivi d'un
                                asterisk <abbr title="Required field">*</abbr></p>
                            <div class="mt-5 text-right md:space-x-3 md:block flex flex-col-reverse">
                                <NuxtLink to="/"><BlankButton insider="Annuler"/></NuxtLink>
                                <GreenButton insider="Se connecter"/>
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
    data() {
        return {
            email: '',
            password: '',
            error: null,
            user: ''
        }
    },
    methods: {
        login() {
            try {
                // Enregistrement de l'utilisateur
                this.$auth.loginWith('local', {
                    data: {
                        identifier: this.email,
                        password: this.password
                    }
                }).then(response => {this.user = response.user.email})
            console.log("Vous êtes connectée");

            this.$router.push('/jante/')
            } catch (e) {
                this.error = e.response.data.message
            }
        }
    }
}

</script>