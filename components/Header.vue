<template>
    <nav id="header" class="bg-gray-700 w-full z-30 top-0 py-1">
        <div class="w-full mx-auto flex flex-wrap items-center justify-between mt-0 px-6 py-3">

            <div class="hidden md:flex md:items-center md:w-auto w-full order-3 md:order-1" id="menu">
                <NuxtLink to="/jante/products"><ButtonNavbar insider="Produits"/></NuxtLink>
                <NuxtLink to="/jante/add"><ButtonNavbar insider="Ajouter un produit"/></NuxtLink>
            </div>

            <div class="ml-5 w-52 flex items-center flex-no-shrink text-white mr-6">
                <!-- <NuxtLink to="/"><img src="../img/japan-racing.png" alt=""></NuxtLink> -->
                <NuxtLink to="/"><p class="font-bold">JAPAN-RACING</p></NuxtLink>
            </div>

            <div class="order-2 md:order-3 flex items-center" id="nav-content">
                <NuxtLink to="/login"><ButtonShadow insider="Se connecter"/></NuxtLink>
            </div>
        </div>
    </nav>
</template>