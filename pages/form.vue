<template>
  <div>
    <div>
      <button
        @click="showSlots"
        class="inline-block px-6 py-2.5 bg-yellow-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full"
      >
        showSlots
      </button>
    </div>

    <div>
      <div class="flex flex-wrap lg:grid-cols-4 sm:grid-cols-4 ml-10">
        <div
          id="cartBg"
          class="bg-green-500 order-2 border-solid border-2 border-black w-1/4 m-4"
          v-for="item in timeSlots"
          v-bind:id="i"
        >
          <div class="p-1 text-center">
            <br />
            <span class="block text-sm font-medium text-slate-700"
              >Start Time-{{ item.startTime }}</span
            >
          </div>
          <br />

          <div class="p-1 text-center">
            <span class="block text-sm font-medium text-slate-700"
              >End Time-{{ item.endTime }}</span
            >
          </div>
          <br />

          <div class="text-center m-2">
            <button
              @click="book"
              type="submit"
              class="inline-block px-6 py-2.5 bg-blue-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-blue-700 hover:shadow-lg focus:bg-blue-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full m-1"
            >
              Book Now
            </button>

            <button
              @click="cancel"
              class="inline-block px-6 py-2.5 bg-red-600 text-white font-medium text-xs leading-tight uppercase shadow-md hover:bg-yellow-700 hover:shadow-lg focus:bg-yellow-700 focus:shadow-lg focus:outline-none focus:ring-0 active:bg-blue-800 active:shadow-lg transition duration-150 ease-in-out rounded-full"
            >
              Cancel
            </button>
          </div>
        </div>
      </div>
    </div>
    <!-- <login/><br><br><br><br><br> -->
  </div>

  <!-- <Admin></Admin> -->
</template>
<script>
//  import Admin1 from '~/pages/admin.vue';

import Admin from "~/pages/admin.vue";
// import login from "~/pages/login.vue";
export default {
  data() {
    return {
      timeSlots: [],
      d: "",
      e: "",
    };
  },
  methods: {
    cancel() {
      document.getElementById("hide").style = "display:none";
    },

    showSlots() {
      var d = new Date("2022-08-01 08:50:00");
      var e = new Date("2022-08-01 09:50:00");
      for (let i = 1; i <= 20; i++) {
        d.setMinutes(d.getMinutes() + 10);
        e.setMinutes(d.getMinutes() + 10);
        this.timeSlots.push({
          startTime: d.toLocaleTimeString(),
          endTime: e.toLocaleTimeString(),
        });
      }
    },
    book() {
      location.href = "http://localhost:3000/admin";
      window.confirm("This Slots is Booked Now");
      document.getElementById("cartBg").style = "background-color:red;";
    },
  },
  components: { Admin },
};
</script>
