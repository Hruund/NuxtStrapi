<template>
    <div class="m-auto max-w-md grid mt-8  gap-8 grid-cols-1">
        <div class="flex flex-col ">
            <div class="bg-white shadow-md rounded-3xl p-5">
                <div class="flex flex-col sm:flex-row items-center">
                    <h2 class="font-semibold text-lg mr-auto m-auto">Connexion</h2>
                </div>
                <div class="mt-5">
                    <div class="form">
                        <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                            <div class="mb-3 md:space-y-2 w-full text-xs">
                                <label class="font-semibold text-gray-600 py-2">Company  Name <abbr title="required">*</abbr></label>
                                <input placeholder="Company Name" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" name="integration[shop_name]" id="integration_shop_name">
                                <p class="text-red text-xs hidden">Please fill out this field.</p>
                            </div>
                            <div class="mb-3 md:space-y-2 w-full text-xs">
                                <label class="font-semibold text-gray-600 py-2">Company  Mail <abbr title="required">*</abbr></label>
                                <input placeholder="Email ID" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" required="required" type="text" name="integration[shop_name]" id="integration_shop_name">
                                <p class="text-red text-xs hidden">Please fill out this field.</p>
                            </div>
                        </div>
                        <div class="md:flex md:flex-row md:space-x-4 w-full text-xs">
                            <div class="w-full flex flex-col mb-3">
                                <label class="font-semibold text-gray-600 py-2">Company Address</label>
                                <input placeholder="Address" class="appearance-none block w-full bg-grey-lighter text-grey-darker border border-grey-lighter rounded-lg h-10 px-4" type="text" name="integration[street_address]" id="integration_street_address">
                            </div>
                            
                        </div>
                        <p class="text-xs text-red-500 text-right my-3">Required fields are marked with an
                            asterisk <abbr title="Required field">*</abbr></p>
                        <div class="mt-5 text-right md:space-x-3 md:block flex flex-col-reverse">
                            <NuxtLink to="/"><BlankButton insider="Annuler"/></NuxtLink>
                            <GreenButton insider="Se connecter" />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  
}
</script>