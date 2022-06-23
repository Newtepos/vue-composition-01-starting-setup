<template>
  <section class="container">
    <h2>{{ user.name }}</h2>
    <h3>{{ user.age }}</h3>
  </section>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup() {
    // const uName = ref('Supakit');
    // const uAge = ref(30);
    const user = reactive({
      name: 'Supakit',
      age: 28,
    });

    console.log(user);

    setTimeout(function () {
      // uName.value = 'Junior';
      // uAge.value = 28;
      user.name = 'Junior';
      user.age = 30;
    }, 2000);

    return { user: user };
  },
  // data() {
  //   return {
  //     userName: 'Maximilian',
  //   };
  // },
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
