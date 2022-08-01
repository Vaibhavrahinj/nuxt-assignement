<template>
  <div>
    <NuxtLink v-slot="{ navigate }" to="/admin" custom>
      <button @click="navigate" class="bg-green-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
         Admin Page
      </button>
    </NuxtLink><br><br>

  <div class="justify justify-center">
   <NuxtLink v-slot="{ navigate }" to="/admin" custom>
      <button @click="navigate" class="bg-red-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
      Admin Form Page
      </button>
    </NuxtLink>
    <br><br>

   <NuxtLink v-slot="{ navigate }" to="/form" custom>
      <button @click="navigate" class="bg-green-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
         Book slot
      </button>
    </NuxtLink>
  </div>
  
</template>

<script>

definePageMeta({
  components:{
    
  }
})
import { reactive } from "vue";


// const state = reactive({ count: 0 });
export default {
    setup() {
        const state = reactive({ count: 0, show: true, mylist:
         [
             
            ]
        });
        return {
           
          
        };
        
    },
};
</script>

<style>

</style>
