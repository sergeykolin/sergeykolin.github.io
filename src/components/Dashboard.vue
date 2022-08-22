<template>
  <div class="dashboard">
    <swiper
       class="swiper"
       :options="swiperOption"
    >
      <swiper-slide class="slide-card" v-for="(item, i) of cards" :key="i">
        <template v-if="item.isTopCard">
          <div class="top-card"  @click="goToPage(item.link)">
            <div class="icon top-amount">
              <div class="icon icon-lightning"></div>
              <span class="top-text">TOP {{item.topAmount}}</span>
            </div>
             <h1 class="top-title">{{item.title}}</h1>
             <p class="top-description"><span v-html="item.description"></span></p>
             <div class="btn-view">Посмотреть</div>
             <div v-if="item.isOneIcon" class="icon icon-top" :style="item.img">
                <div v-for="(flag, i) of item.flagIcons" :key="i" class="icon icon-flag" :style="flag"></div>
             </div>
             <div v-else class="top-icons icon-top">
              <div v-for="(icon, i) of item.imgs" :key="i" class="icon icon-mini" :style="icon"></div>
             </div>
          </div>
        </template>
         <template v-else>
          <div class="second-card" @click="goToPage(item.link)">
            <div class="icon icon-second">
              <div class="icon icon-second-img" :style="item.img"></div>
            </div>
            <h1 class="second-text">{{item.title}}</h1>
            <p class="second-text"><span v-html="item.description"></span></p>
          </div>
         </template>
      </swiper-slide>
      <swiper-slide class="slide-stub"></swiper-slide>
    </swiper>
  </div>
</template>

<script>
  import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  import 'swiper/css/swiper.css'

export default {
  name: 'DashboardPage',
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 4,
        spaceBetween: 30,
        centeredSlides: true,
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        }
      },
      cards: [
          {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild6632-3333-4232-a662-383164323032/-/cover/568x320/center/center/-/format/webp/minimap-min.png)' },
          title: 'Квартиры под аренду',
          description: 'Квартиры с доходностью<br>12% годовых в Дубаи',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
          isTopCard: true,
          topAmount: 50,
          isOneIcon: true,
          flagIcons: [
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3062-3530-4365-a537-663063386564/-/cover/66x72/center/center/-/format/webp/star-realiste.png)',
              margin: '110px',
              position: 'absolute'
            },
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3433-3430-4463-b263-623830373134/-/cover/66x72/center/center/-/format/webp/star.png)',
              margin: '150px 130px',
              position: 'absolute'
            },
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3062-3530-4365-a537-663063386564/-/cover/66x72/center/center/-/format/webp/star-realiste.png)',
              margin: '60px 180px',
              position: 'absolute'
            },
              {
              'background-image': 'url(https://thumb.tildacdn.com/tild3433-3430-4463-b263-623830373134/-/cover/66x72/center/center/-/format/webp/star.png)',
              margin: '100px 240px',
              position: 'absolute'
            },
          ]
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild6632-3333-4232-a662-383164323032/-/cover/568x320/center/center/-/format/webp/minimap-min.png)' },
          title: '100 квартир для инвестиций',
          description: 'Рейтинг квартир для<br>инвестиций в Дубаи',
          link: 'https://realiste.io/search?utm_anim=1',
          isTopCard: true,
          topAmount: 100,
          isOneIcon: true,
          flagIcons: [
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3433-3430-4463-b263-623830373134/-/cover/66x72/center/center/-/format/webp/star.png)',
              margin: '120px 180px',
              position: 'absolute'
            },
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3433-3430-4463-b263-623830373134/-/cover/66x72/center/center/-/format/webp/star.png)',
              margin: '150px 130px',
              position: 'absolute'
            },
            {
              'background-image': 'url(https://thumb.tildacdn.com/tild3062-3530-4365-a537-663063386564/-/cover/66x72/center/center/-/format/webp/star-realiste.png)',
              margin: '60px 180px',
              position: 'absolute'
            },
              {
              'background-image': 'url(https://thumb.tildacdn.com/tild3433-3430-4463-b263-623830373134/-/cover/66x72/center/center/-/format/webp/star.png)',
              margin: '100px 240px',
              position: 'absolute'
            },
          ]
        },
        {
          imgs: [
            { 'background-image': 'url(https://thumb.tildacdn.com/tild3037-6535-4333-a232-653561346165/-/cover/276x152/center/center/-/format/webp/__2022-07-11__40828_.png)' },
            { 'background-image': 'url(https://thumb.tildacdn.com/tild3139-6431-4263-b935-633337393337/-/cover/276x152/center/center/-/format/webp/__2022-07-11__41822_.png)' },
            { 'background-image': 'url(https://thumb.tildacdn.com/tild3731-3535-4038-b765-333430383864/-/cover/276x152/center/center/-/format/webp/__2022-07-11__41018_.png)' },
            { 'background-image': 'url(https://thumb.tildacdn.com/tild6635-3363-4530-b535-633136633564/-/cover/276x152/center/center/-/format/webp/__2022-07-11__40855_.png)' },
          ],
          title: 'Самые престижные проекты',
          description: 'Квартиры в домах где<br>живут миллионеры',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
          isTopCard: true,
          topAmount: 30,
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild3231-6663-4330-b431-316232336639/-/cover/130x130/center/center/-/format/webp/appartmentsInCircle.png)' },
          title: 'Квартиры',
          description: 'Квартиры по ценам<br>ниже рыночных',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild3763-3733-4834-a264-356331613135/-/cover/130x130/center/center/-/format/webp/FundsInCircle.png)' },
          title: 'Сделки',
          description: 'История сделок<br>с недвижимостью',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild3730-6466-4466-b036-613365336136/-/cover/130x130/center/center/-/format/webp/TradeUpInCircle.png)' },
          title: 'Обмен',
          description: 'Обмен вашей квартиры<br>на новую',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild3961-3934-4230-b231-333733363238/-/cover/130x130/center/center/-/format/webp/EstimationInCircle.png)' },
          title: 'Оценка',
          description: 'Оцените квартиру<br>за 10 секунд',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
        },
        {
          img: { 'background-image': 'url(https://thumb.tildacdn.com/tild6533-3937-4433-b761-613066363331/-/cover/130x130/center/center/-/format/webp/IndexInCircle.png)' },
          title: 'Индексы',
          description: 'Индекс цен и ликвидность<br>районов',
          link: 'https://ru-ae.realiste.io/?cenLat=25.07704324&cenLng=55.133523&zoom=12&discountFromPriceMarketMin=0.03&discountFromPriceMarketMax=0.4&priceMin&priceMax&selectedCity=Dubai&payExtraGetCash=both',
        }
      ]
    }
  },
  methods: {
    goToPage(link) {
      window.open(link, '_self');
    }
  },
}
</script>

<style scoped>
  .dashboard {
    height: calc(100vh - 140px);
    width: 100vw !important;
    max-width: 100%;
    cursor: grab;
  }

  .swiper-container {
    height: 100%;
    overflow-x: visible;
  }

  .swiper-slide {
    width: 60%;
  }

  .swiper-slide:nth-child(2n) {
      width: 40%;
  }

  .swiper-slide:nth-child(3n) {
      width: 20%;
  }

  .slide-card {
    cursor: pointer;
    width: 330px !important;
    height: 500px !important;
    border-radius: 20px;
    background: rgba(0,0,0,0.0);
    background-position: center center;
    border: none;
    box-shadow: 2px 6px 20px 4px rgb(0 0 0 / 20%);
    align-self: center;
  }

  .icon {
    background-position: center center;
    background-size: cover;
    background-repeat: no-repeat;
    border-color: transparent;
    border-style: solid;
    justify-self: center;
  }

  .icon-second-img {
    height: 90px;
    width: 90px;
    align-self: center;
  }

  .icon-second {
    display: grid;
    justify-content: center;
    height: 150px;
    width: 200px;
    background-image: url('https://thumb.tildacdn.com/tild3938-3763-4663-b736-633866323932/-/cover/488x484/center/center/-/format/webp/EstimationBG-min.png');
  }

  p {
    font-size: 20px;
    font-weight: 500;
    margin: 0;
    color: #222;
  }

  h1 {
    margin: 0;
    font-weight: 900;
    color: #222;
  }

  .second-card {
    display: grid;
    height: 100%;
    align-content: center;
  }

  .top-card {
    height: 100%;
    display: grid;
    text-align: left;
    padding: 0 15px;
    align-items: flex-end;
  }

  .second-text {
    margin: auto;
  }

  .icon-top {
    width: 100%;
    height: 200px;
    border-radius: 20px;
    align-self: center;
  }

  .top-icons {
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    align-content: space-between;
  }

  .btn-view {
    color: #202124;
    font-size: 18px;
    line-height: 32px;
    font-weight: 700;
    border-radius: 30px;
    background-color: #ffffff;
    background-position: center center;
    border-color: transparent;
    border-style: solid;
    width: 120px;
    height: 34px;
    text-align: center;
    align-self: flex-start;
  }

  .top-amount {
    background-image: url('https://static.tildacdn.com/tild3962-6330-4034-b264-383438626139/ezgif-2-af3868226f.gif');
    border-radius: 50px;
    width: 80px;
    height: 20px;
    align-self: end;
    justify-self: auto;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .icon-lightning {
    background-image: url('https://static.tildacdn.com/tild3938-3866-4163-a666-373763376438/bolt.svg');
    width: 10px;
    height: 13px;
  }

  .top-title {
    line-height: 30px;
  }

  .top-description {
    align-self: center;
  }

  .top-text {
    color: #fff;
    font-size: 14px;
    font-weight: 900;
  }

  .icon-mini {
    height: 95px;
    width: 145px;
    border-radius: 20px;
  }

  .icon-flag {
    height: 40px;
    width: 40px;
  }

  .slide-stub {
    width: 1px !important;
  }
</style>
