<template>
  <div>
    <p>helo gulam from hello world</p>
    <!-- <span>{{todo.name}}</span> -->
  </div>
</template>
<script>
export default {
  name: "helloWorld",
  props: {
    parentData: Object,
    stringProp: String,
    title: String
  },

  data() {
    return {
      formData: "jkhjhjkhjkh"
    };
  }
};
</script>