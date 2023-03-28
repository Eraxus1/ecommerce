<template>
  <div>
    <h1>About Page</h1>
    <p>Welcome to my about page!</p>
    <AnotherComponent />
  </div>
</template>


<script>
import AnotherComponent from "@/components/AnotherComponent.vue";

export default {
  components: {
    AnotherComponent,
  },
};
</script>
