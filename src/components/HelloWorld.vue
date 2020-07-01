<template>
  <div class="bg-indigo-200 text-indigo-900">
    <pre>
      {{$data}}
    </pre>

    <input type="text" v-model="newElement" @keyup.enter="addElement" required>

    <!-- add element array -->
    <button class="bg-teal-600 text-green-100 px-3 py-2 mt-3 focus:outline-none rounded-lg" :class="[newElement.length === 0 ? 'opacity-50 pointer-events-none' : 'bg-green-400']" 
            @click="addElement"> +
    </button>

    <!-- clear array -->
    <button class="p-2 bg-red-600 focus:outline-none rounded-lg mx-2" @click="cleanElement">
        Clear
    </button>

    <ul>
      <li v-for="(item, key) in list" :key="key">
        <div class="text-left">
          [Index: {{ key }}] {{ item }}
        </div>
      </li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  
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
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
