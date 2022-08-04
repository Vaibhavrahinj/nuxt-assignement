<template>
  <div>
    <div
      class="border-solid border-2 border-black-600 w-1/3 m-auto mt-20"
      id="hidden"
    >
      <table>
        <tr>
          <td><label for="userName" class="m-5 p-5">UserName</label></td>
          <td>
            <input
              type="text"
              autocomplete="off"
              class="bg-white-500 m-5 p-5 border-solid border-2 border-black-600"
              id="userName"
              v-model.lazys="loginDetails.userName"
              placeholder="UserName"
            />
          </td>
        </tr>
        <tr>
          <td><label class="m-5 p-5" for="pass">Password</label></td>
          <td>
            <input
              class="bg-white-500 m-5 p-5 border-solid border-2 border-black-600"
              type="password"
              v-model="loginDetails.pass"
              id="pass"
              placeholder="Enter the password"
            />
          </td>
        </tr>
      </table>
      <!-- <p>{{loginDetails.userName}}</p> -->
      <button
        class="ml-28 mb-7 p-5 w-1/2 bottom-2 border border-gray-900 rounded-md hover:bg-gray-700"
        @click="login"
      >
        Login
      </button>
    </div>
  </div>
</template>
<script setup>
const loginDetails = reactive({
  userName: "",
  pass: "",
});
function login() {
  if (loginDetails.userName == "vaibhav" && loginDetails.pass == "vaibhav") {
    alert("Login Successfull");
    location.href = "http://localhost:3000/form";
  } else {
    alert("Please Enter correct Uname and Pass");
  }
}
</script>
