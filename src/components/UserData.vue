<template>
  <h2>{{ userName }}</h2>
  <h3>{{ age }}</h3>
</template>

<script>
import {
  computed,
  inject,
  onBeforeMount,
  onMounted,
  onUpdated,
  onBeforeUpdate,
  onUnmounted,
} from 'vue';

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

    onBeforeMount(function () {
      console.log('onBeforeMount');
    });

    onMounted(function () {
      console.log('onMounted');
    });

    onBeforeUpdate(function () {
      console.log('onBeforeUpdate');
    });

    onUpdated(function () {
      console.log('onUpdated');
    });

    onUnmounted(function () {
      console.log('onUnmounted');
    });

    // context.emit('save-data'); //this.$emilt('save-data')

    return {
      userName: uName,
      age,
    };
  },
};
</script>
