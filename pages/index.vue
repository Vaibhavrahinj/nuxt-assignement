<template>
<login/><br><br><br><br><br>
</template>

<script>

definePageMeta({
  components:{
    
  }
})
import { reactive } from "vue";
import login from "~/pages/login.vue";
//  import form from '~/pages/form.vue';
import Form from "~/pages/form.vue";
// import Admin from "~/pages/admin.vue";
import Admin1 from "~/pages/admin.vue";

// const state = reactive({ count: 0 });
export default {
    setup() {
        const state = reactive({ count: 0, show: true, mylist: []
        });
        // reactive method using this method we can add object and array also
        // expose the state to the template

        return {
            Form,
            Admin1,
            login,
        };
        
    },
    components: { Form, Admin1,login }
};
</script>

<style>

</style>
