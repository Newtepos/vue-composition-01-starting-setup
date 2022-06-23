<template>
  <section class="container">
    <h2>{{ uName }}</h2>
    <h3>{{ age }}</h3>
    <button @click="setAge">Change Age</button>
    <div>
      <input type="text" placeholder="First Name" @input="setFirstName" />
      <input type="text" placeholder="Last Name" @input="setLastName" />
    </div>
  </section>
</template>

<script>
import { reactive, ref, toRefs, computed } from 'vue';

export default {
  setup() {
    const firstName = ref('');
    const lastName = ref('');
    const user = reactive({
      name: 'Supakit',
      age: 28,
    });

    const uName = computed(function () {
      return firstName.value + ' ' + lastName.value;
    });

    function setNewAge() {
      user.age = 32;
    }

    function setFirstName(e) {
      firstName.value = e.target.value;
    }

    function setLastName(e) {
      lastName.value = e.target.value;
    }

    const userRefs = toRefs(user);

    return {
      user: user,
      userName: userRefs.name,
      age: userRefs.age,
      setAge: setNewAge,
      setFirstName,
      setLastName,
      uName,
    };
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
