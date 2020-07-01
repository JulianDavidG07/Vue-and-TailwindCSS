<template>
  <div>
    <div class="flex justify-center bg-teal-300">
      <span class="text-white text-sm mb-3 mt-1 px-2 rounded-full bg-black">
          Vue Router <span class="bg-white text-black rounded-lg py-0 mt-5">></span>
      </span>

      <router-link to="/" class="font-medium mx-5 bg-teal-500 px-2 hover:bg-teal-700" exact>ListArray</router-link> |
      <router-link to="/about" class="font-medium mx-5 bg-teal-500 px-2 hover:bg-teal-700">ProgressBar</router-link>
    </div>
    <router-view/>
  </div>
</template>
