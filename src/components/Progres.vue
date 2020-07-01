<template>
    <div>

        <pre>{{$data}}</pre>
        
        <div class="rounded-lg h-5 px-8 mt-5" :style="`width: ${count}%`">
            <div :class="modifyColor">
                {{count}}%
            </div>
        </div>

        <div class="mt-3 ">
            <button class="rounded-md mr-5 px-3 py-1 focus:outline-none" 
                    :class="[count === 0 ? 'pointer-events-none opacity-25 bg-red-500': 'bg-red-500']" 
                    @click="count = count - 10"
                    >
                -
            </button>

            <button class="bg-green-500 rounded-md px-3 py-1 focus:outline-none"  
                    :class="[count === 100 ? 'pointer-events-none opacity-25 bg-green-500' : 'bg-green-500']"
                    @click="count = count + 10"
                    >
                +
            </button>
    
        </div>
    </div>
</template>

<script>
export default {
    name: 'Progres',

    data() {
        return {
            count: 10
        }
    },

    computed: {
        modifyColor() {
            return {
                'bg-red-700' : this.count <= 10,
                'bg-red-500' : this.count > 10 && this.count <= 20,
                'bg-orange-400' : this.count > 20 && this.count <= 40,
                'bg-yellow-400' : this.count > 40 && this.count <= 70,
                'bg-green-400' : this.count > 70 && this.count <= 99,
                'bg-teal-500' : this.count === 100
                }
            },
    }

}
</script>
