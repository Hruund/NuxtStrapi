<template>
<div class="bg-gray-50 w-full">
  <div class="container w-2/4">
    <div>
      <h1 class="title font-bold">
        SITE DE JANTE EN LIGNE
      </h1>
      <div class="flex flex-col items-center m-8">
        <div class="w-full bg-white rounded overflow-x-hidden flex snap-x" style="height: 40vh">
          <div class="snap-start w-full h-full flex items-center justify-center text-white text-4xl font-bold flex-shrink-0 bg-black relative" id="slide-1">
            <img src="../img/slide1.jpg" class="h-full w-full object-contain absolute inset-0 z-10">
          </div>
          <div class="snap-start w-full h-full flex items-center justify-center text-white text-4xl font-bold flex-shrink-0 bg-black relative" id="slide-2">
            <img src="../img/slide2.jpg" class="h-full w-full object-cover absolute inset-0 z-10">
          </div>
          <div class="snap-start w-full h-full flex items-center justify-center text-white text-4xl font-bold flex-shrink-0 bg-black relative" id="slide-3">
            <img src="../img/slide3.jpg" class="h-full w-full object-cover absolute inset-0 z-10">
          </div>
        </div>
        <div class="flex mt-8">
          <a class="w-8 mr-1 h-8 text-gray-700 rounded-full bg-white flex justify-center items-center" href="#slide-1">1</a>
          <a class="w-8 mr-1 h-8 text-gray-700 rounded-full bg-white flex justify-center items-center" href="#slide-2">2</a>
          <a class="w-8 mr-1 h-8 text-gray-700 rounded-full bg-white flex justify-center items-center" href="#slide-3">3</a>
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
      items: []
    }
  },
  methods: {
    
  },
  destroyed () {
    //
  }
}
</script>

<style>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
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
  display: block;
  font-weight: 300;
  font-size: 70px;
  font-style: bold;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}

.snap-x {
    scroll-snap-type: x mandatory;
    
  scroll-behavior: smooth;
  -webkit-overflow-scrolling: touch;
}
.snap-start {
  scroll-snap-align: start;
}

.body {
  background-color: bisque;
}
</style>
