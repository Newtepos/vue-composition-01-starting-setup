<template>
  <h2>{{ userName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script>
import { computed, inject } from 'vue';

export default {
  props: ['firstName', 'lastName'],
  //   computed: {
  //     userName() {
  //       return this.firstName + ' ' + this.lastName;
  //     },
  //   },
  setup(props, context) {
    const uName = computed(function () {
      return props.firstName + ' ' + props.lastName;
    });

    const age = inject('user-age');

    console.log(context);

    // context.emit('save-data'); //this.$emilt('save-data')

    return {
      userName: uName,
      age,
    };
  },
};
</script>
