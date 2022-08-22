<template>
    <div class="footer">
       <div class="item-block" v-for="(item, i) of footerList" :key="i">
        <div class="img" :style="item.imgPath"></div>
        <p>{{item.text}}</p>
       </div>
    </div>
</template>

<script>
export default {
  name: 'FooterApp',
  data() {
    return {
      footerList: [
        { imgPath: { 'background-image': 'url(https://static.tildacdn.com/tild3235-3331-4662-a435-376239636236/appartments.svg)' }, text: 'Квартиры' },
        { imgPath: { 'background-image': 'url(https://static.tildacdn.com/tild6633-6631-4662-a135-326538383531/funds.svg' }, text: 'Сделки' },
        { imgPath: { 'background-image': 'url(https://static.tildacdn.com/tild3035-3530-4561-b734-336530653164/Estimation.svg' }, text: 'Оценка' },
        { imgPath: { 'background-image': 'url(https://static.tildacdn.com/tild6266-3936-4638-a633-623437393439/TradeUp.svg' }, text: 'Обмен' },
        { imgPath: { 'background-image': 'url(https://static.tildacdn.com/tild6461-3466-4633-b761-343765663965/Index.svg' }, text: 'Индекс' },
      ],
    }
  },
}
</script>

<style scoped>
  .footer {
    width: 100vw !important;
    height: 70px;
    max-width: 100%;
    display: flex;
    justify-content: center;
  }

  p {
    font-size: 16px;
    font-weight: 900;
    margin: auto;
  }

  .img {
    width: 40px;
    height: 40px;
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
    border-color: transparent;
    border-style: solid;
    margin: auto;
  }

  .item-block {
    cursor: pointer;
    width: 100px;
  }
</style>
