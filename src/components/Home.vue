<template>
  <div class="home">
    <img class="logo" src="../assets/logo.png">

    <div class="input-group">
      <label>Private Key:</label>
      <input v-model="pk" />
    </div>
    <div class="input-group">
      <label>RPC Url:</label>
      <input v-model="url" />
    </div>
    <div class="input-group">
      <button class="primary" v-on:click="go">GO</button>
    </div>
  </div>
</template>

<script>
import router from '../router'

export default {
  name: 'Home',

  methods: {
    go() {
      localStorage.setItem('pk', this.pk);
      localStorage.setItem('url', this.url);
      router.push('wallet');
    }
  },

  data () {
    return {
      pk: localStorage.getItem('pk'),
      url: localStorage.getItem('url')
    };
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  width: 600px;
}
</style>
