<template>
  <main class="flex justify-center w-full h-screen">
    <div>
      <form
        @submit="formSubmit"
        class="bg-gray-100 border-blue-400 rounded-lg border-2 px-12 bg-gradient-to-r to-blue-200"
      >
        <table>
          <h2 class="text-red-900 text-xl font-bold pt-6">Admin Form</h2>
          <hr />
          <label class="pt-10 py-10" for="firstname">
            <span class="block text-sm font-medium text-slate-700"
              >UserName</span
            > </label
          ><br />
          <input
            type="text"
            v-model="user.firstname"
            id="firstname"
            name="firstname"
            required
            placeholder="Enter your first name"
            class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md text-sm shadow-sm placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:bg-slate-50 disabled:text-slate-500 disabled:border-slate-200 disabled:shadow-none invalid:border-pink-500 invalid:text-pink-600 focus:invalid:border-pink-500 focus:invalid:ring-pink-500"
          /><br /><br />

          <label for="number" class="block">
            <span class="block text-sm font-medium text-slate-700"
              >Password</span
            > </label
          ><br />
          <input
            type="number"
            v-model="user.number"
            id="number"
            name="number"
            required
            placeholder="Enter your Mobile Number"
            class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md text-sm shadow-sm placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-1 focus:ring-sky-500 disabled:bg-slate-50 disabled:text-slate-500 disabled:border-slate-200 disabled:shadow-none invalid:border-pink-500 invalid:text-pink-600 focus:invalid:border-pink-500 focus:invalid:ring-pink-500"
          />
          <br /><br />
          <button
            class="py-1 px-5 mr-5 bg-black hover:bg-cyan-500 shadow-lg shadow-cyan-500/50 text-white font-bold text-center rounded-md mb-3"
            type="submit"
            @click="formSubmit"
            id="btnsub"
          >
            Submit
          </button>
          <button
            class="py-1 px-5 bg-black hover:bg-cyan-500 shadow-lg shadow-cyan-500/50 text-white font-bold text-center rounded-md mb-3"
            type="reset"
          >
            Reset
          </button>
        </table>
      </form>
      <br />

      <table class="list">
        <tr>
          <th class="px-4 border-red-400 rounded-lg border-4">First Name</th>
          <th class="px-4 border-red-400 rounded-lg border-4">Contact No</th>
          <th class="px-4 border-red-400 rounded-lg border-4">Action</th>
        </tr>
        <tr v-for="(item, index) in users" v-bind:index="index" :key="item">
          <td class="px-4 border-red-100 rounded-lg border-4">
            {{ item.firstname }}
          </td>
          <td class="px-4 border-red-100 rounded-lg border-4">
            {{ item.number }}
          </td>
          <td class="px-4 border-red-100 rounded-lg border-4">
            {{ item.Action }}

            <button
              class="mx-3 rounded-lg bg-green-600 hover:bg-green-600 text-white w-20"
              @click="onEdit(index)"
            >
              Edit
            </button>
          </td>
        </tr>
      </table>
    </div>
  </main>
</template>
<script>
export default {
  data() {
    return {
      isEdit: false,
      indexEdit: -1,
      users: [],
      user: {
        firstname: "",
        number: "",
      },
    };
  },
  methods: {
    formSubmit(event) {
      event.preventDefault();
      document.getElementById("btnsub").innerHTML = "Submit";
      if (this.isEdit == true) {
        this.users[this.indexEdit] = this.user;
        this.isEdit = false;
        this.indexEdit = -1;
        alert("Successfully Updated");
      } else {
        this.users.push(this.user);
        alert("Data Added");
      }
      this.user = {
        firstname: "",
        number: "",
      };
    },
    onReset(event) {
      event.preventDefault();
      this.form.name = "";
      this.form.city = "";
    },
    // userDelete(index) {
    //     this.users.splice(index, 1)
    // },
    onEdit(index) {
      document.getElementById("btnsub").innerHTML = "Update";
      this.user.firstname = this.users[index].firstname;
      this.user.number = this.users[index].number;
      this.isEdit = true;
      this.indexEdit = index;
    },
  },
};
</script>
