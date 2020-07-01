<template>
  <div class="bg-indigo-200 text-gray-900">

    <p class="text-black font-light mx-4 my-2">Component that shows the process of how elements are added to DATA, and how they are added with @click events and these are activated or deactivated depending on whether or not there is information</p>

    <div>
      <input type="text" class="block w-full p-2 px-3 bg-orange-100 border border-orange-500 rounded-md focus:bg-orange-200 focus:border-2 focus:border-indigo-800" v-model="newElement" @keyup.enter="addElement" placeholder="Add elements" >
  
      <div class="flex justify-center">
        <!-- add element array -->
        <button class="bg-teal-600 text-green-100 px-3 py-2 mt-3 focus:outline-none rounded-lg my-2"
                :class="[newElement.length === 0 ? 'opacity-50 pointer-events-none' : 'bg-green-400']" 
                @click="addElement"> +
        </button>
    
        <!-- delete element element array -->
        <button class="text-red-100 px-3 py-2 mt-3 focus:outline-none rounded-lg mx-2 my-2"
                :class="[list.length === 0 ? 'opacity-50 pointer-events-none bg-orange-600' : 'bg-orange-600']"
                @click="deleteElement"> -
        </button>
    
        <!-- clear array -->
        <button class="px-2 bg-red-600 focus:outline-none rounded-lg my-2" @click="cleanElement">
            Clear
        </button>
      </div>
    </div>

    <div class="block md:flex">
      <pre class="block bg-gray-800 text-white md:w-1/2">
      <span class="text-white text-xs bg-black px-2 rounded-lg font-bold flex w-12 ml-3 h-4">-Vue</span>
        {{$data}}
      </pre>

      <ul class="block md:w-1/2 bg-gray-600 text-black">
        <span class="text-white text-xs bg-black px-2 rounded-lg font-bold flex w-16 ml-3 mt-5">Render</span>
        <li v-for="(item, key) in list" :key="key">
          <div class="text-left md:mx-64">
            [Key: {{ key }}] {{ item }}
          </div>
        </li>
      </ul>
    </div>

  </div>
</template>

<script>
export default {
  name: 'List',
  
  data() {
    return {
      newElement: '',
      list: [],
    }
  },

  methods: {
    addElement() {
      this.list.push(this.newElement)
      this.newElement = ''
    },

    cleanElement() {
      this.list = []
    },

    deleteElement() {
      this.list.pop()
    }
  }
}
</script>

