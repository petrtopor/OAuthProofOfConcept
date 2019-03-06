<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png" />
    <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
    <div id="link">
      <span @click="onClick">Authorize</span>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import { error } from 'util';
export default {
  name: "home",
  components: {
    HelloWorld
  },
  methods: {
    onClick() {
      window.location.href = 'https://oauth.yandex.ru/authorize?response_type=token&client_id=63b447abead34a81aae6b03a537196cb'
      // window.open('https://oauth.yandex.ru/authorize?response_type=token&client_id=63b447abead34a81aae6b03a537196cb')
      /*
      axios.post('https://oauth.yandex.ru/authorize?response_type=token&client_id=63b447abead34a81aae6b03a537196cb').then(response => {
        console.log(response)
      }).catch(error => {
        console.log(error)
      })
      */
    }
  }
};
</script>

<style lang="scss" scoped>
.home {
  #link {
    height: 16px;
    width: 64px;
    background-color: black;
    cursor: pointer;
    span {
      font-size: 20px;
      color: azure;
      cursor: pointer;
    }
  }
}
</style>
