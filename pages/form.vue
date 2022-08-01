<template>
  <main class="flex justify-center w-full h-screen">
    <div>
     
      <div>
        <div

          class="flex justify-between w-full lg:grid-cols-6 md:grid-cols-4 sm:grid-cols-1"

          class=" w-full "

        
          <div class="shadow-inner">
            <div class="rounded-lg shadow-lg bg-white max-w-sm">
              <div class="p-8">
                 <form @submit="formSubmit">
                <div>
                <span class="block text-sm font-medium text-slate-700">Start Date</span>
                <br> {{startTime}}
                <input id="start" type="date" aria-required="false"/>
                </div>

                    <div><br>
                <span class="block text-sm font-medium text-slate-700">End Date</span>
                <br> {{endTime}}
                <input id="end" type="date" aria-required="false"/>
                </div><br>
                 <button @click="formSubmit" id="btnsub" 
                  type="submit"
                  class="inline-block px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full"
                >
                  Book Now
                </button>

               
                 </form>
               
              </div>
            </div>
          </div>


          <!-- card -->


           

         
        </div>
      </div>
    </div>
  </main>
  
</template>

<script>


export default {
   data() {
      return {
         data:new Date
      }
   },
    methods: {
   
         formSubmit(event) {
            event.preventDefault();
           var start= document.getElementById("start").value;
           var end= document.getElementById("end").value;
           
           alert('Starting date '+start +'   '+'Ending Date ' + end );
                
        }
  },
}
</script>
