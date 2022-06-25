<template>
  <h2>{{ userName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script>
import { computed } from '@vue/reactivity';

export default {
  props: ['age', 'firstName', 'lastName'],
  //   computed: {
  //     userName() {
  //       return this.firstName + ' ' + this.lastName;
  //     },
  //   },
  setup(props, context) {
    const uName = computed(function () {
      return props.firstName + ' ' + props.lastName;
    });

    console.log(context);

    return {
      userName: uName,
    };
  },
};
</script>
