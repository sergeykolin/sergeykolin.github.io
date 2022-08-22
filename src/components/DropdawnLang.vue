<template>
    <div class="menu-lang" @click="isOpen = !isOpen">
        <img src="https://static.tildacdn.com/tild6239-6138-4939-b337-656661633336/globe.svg">
        <transition name="lang" appear>
          <div class="sub-menu" v-if="isOpen">
            <div v-for="(item, i) of langs" :key="i" class="menu-item">
              <a href="#">{{item.name}}</a>
            </div>
          </div>
        </transition>
    </div>
</template>

<script>
export default {
  name: 'DropdawnLang',
  data() {
    return {
        langs: [
            { name: 'РУССКИЙ'},
            { name: 'ENGLISH'},
        ],
        isOpen: false,
    }
  },
}
</script>

<style scoped>
  .menu-lang {
    width: 80px;
  }

  img {
    cursor: pointer;
  }

  .sub-menu {
    background-color: #fff;
    border-radius: 0 0 16px 16px;
    position: absolute;
    transform: translateX(-50%) translateY(-100%);
    text-align: center;
    color: #fff;
    padding: 4px 2px;
    content: "";
    position: absolute;
    transform: translateX(-50%);
    border-width: 4px 6px 0 6px;
    border-style: solid;
    border-color: rgba(0,0,0,0.7) transparent transparent transparent;
    z-index: 100;
  }

  a {
    color: #222;
    text-decoration: none;
    font-size: 16px;
    font-weight: bold;
  }
</style>