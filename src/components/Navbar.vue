<template>
    <div class="header">
      <div class="logo"></div>
      <DropdawnLang></DropdawnLang>
    </div>
</template>

<script>
import DropdawnLang from './DropdawnLang.vue'
export default {
  name: 'NavbarHeader',
  components: {
    DropdawnLang
  }
}
</script>

<style scoped>
  .header {
    height: 70px;
    max-width: 100%;
    display: flex;
    align-items: center
  }

  .logo {
    width: 150px;
    height: 34px;
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
    border-color: transparent;
    border-style: solid;
    margin: auto;
    background-image: url('https://static.tildacdn.com/tild3735-3963-4137-a439-623033616465/Realiste_rus_logo.svg');
  }
</style>
