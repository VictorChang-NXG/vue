<template>
  <div>
    <input type="text" v-bind:value="msg" v-on:input="changeMessage">
    <p>{{ message }}</p>
  </div>
</template>

<script>
  export default {
      props: ['msg'],
      data() {
          return {
              message: ''
          }
      },
      methods: {
          changeMessage(){
              this.message = event.target.value;
              this.$emit('messageChanged',this.message);
          }
      }
  }
</script>
