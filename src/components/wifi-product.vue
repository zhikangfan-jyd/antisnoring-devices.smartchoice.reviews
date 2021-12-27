<template>
  <div class="product-wrapper">
      <div :class="{'product-item': true, 'first-item': index == 0, 'last-item': index == productList.length - 1}" v-for="(product,index) in productList" :key="index">
          <div class="circle" v-if="index != productList.length- 1">
              <span class="num">{{index + 1}}</span>
          </div>
          <div class="corner-box" v-if="index == 0">
              <span class="text">40% Discount Today!</span>
          </div>
          <div class="big-title" v-if="index == productList.length - 1">The Most Popular Anti-Snoring Device In 2021</div>
          <a :href="product.link" target="_blank" class="product-link-box">
            <div class="product-container">
                <div class="product-container-left">
                    <div class="picture-box">
                        <img :src="product.picture" :alt="product.name" class="picture">
                    </div>
                    <div class="desc-list-box">
                        <h2 class="product-name">{{product.name}}</h2>
                        <ul class="list-box" v-if="product.strengthList.length != 0">
                            <li v-for="(item,id) in product.strengthList" :key="id">
                                <span class="icon"></span>
                                <p class="text">{{item.text}}</p>
                            </li>
                        </ul>
                        <ul class="list-box weakness-list" v-if="product.weaknessList.length != 0">
                            <li v-for="(item,id) in product.weaknessList" :key="id">
                                <span class="icon"></span>
                                <p class="text">{{item.text}}</p>
                            </li>
                        </ul>
                        <p class="buys" v-if="index == 0 || index == productList.length - 1">Buy 3 Get 2 Free NOW</p>
                    </div>
                </div>
                <div class="product-container-right">
                    <p class="good">
                        <span class="text">{{index == 0 || index == productList.length - 1 ? 'Excellent': index == 1 ? 'Very Good': 'Good'}}</span>
                        <span class="king-icon" v-if="index == 0 || index == productList.length - 1"></span>
                        <span class="good-icon" v-if="index == 1"></span>
                    </p>
                    <p class="rate-box"><span class="score">{{product.score}}</span><span>/10</span></p>
                    <a :href="product.link" target="_blank" class="btn">
                        <span class="text">Visit Site</span>
                        <span class="icon"></span>
                    </a>
                    <!-- <a :href="product.reviewLink" class="review">Read Our Review</a> -->
                </div>
            </div>
          </a>
      </div>
      
  </div>
</template>

<script>
export default {
    data() {
        return {
            productList: [
                {
                    id: 1,
                    name: 'SilentSnore',
                    picture: require('../assets/image/snoring/stopSnoreClip1.png'),
                    link: 'https://newxventions.com/intl_7/?prod=silentsnore&net=9785&aff={AFFID}&sid={SUBID}&cid={CLICKID}',
                    reviewLink: '',
                    buys: 586,
                    strengthList: [
                        {
                            text: 'Best Anti Snoring Device In The Market'
                        },
                        {
                            text: 'Eco-Friendly 100% Silicone Gel'
                        },
                        {
                            text: 'Super Easy To Use'
                        },
                        {
                            text: 'Solves Snoring Once And For All'
                        },
                        {
                            text: 'Easy To Clean And Reusable'
                        },
                        {
                            text: 'Helps Reduce Dry Mouth'
                        },
                        {
                            text: 'Extremely Low Price'
                        }
                    ],
                    weaknessList: [],
                    score: '10'

                },
                {
                    id: 2,
                    name: 'Sleep Connection',
                    picture: require('../assets/image/snoring/sleepConnection.png'),
                    link: 'https://www.edlwss.com/88MJP83/4CF3291/?uid=3952',
                    reviewLink: '',
                    buys: 586,
                    strengthList: [
                        {
                            text: 'Stop Snoring From The First Night'
                        },
                        {
                            text: 'Just Put On the Wrist And It Starts'
                        },
                        {
                            text: 'Initiate With Single Button Press'
                        },
                        {
                            text: 'Automatic Power Off After 8 Hours'
                        },
                        {
                            text: 'Lightweight, Non-Invasive Wearable Technology'
                        }
                    ],
                    weaknessList: [
                        {
                          text: 'Higher price than other competitors'  
                        }
                    ],
                    score: '9.6'

                },
                {
                    id: 3,
                    name: 'Snore Strap',
                    picture: require('../assets/image/snoring/snoreStrap.png'),
                    link: 'https://buysmartproduct.com/intl/?prod=snorestrap&net=9785&aff={AFFID}&sid={SUBID}&cid={CLICKID}',
                    reviewLink: '',
                    buys: 586,
                    strengthList: [
                        {
                            text: 'Helps You and Your Partner to Have a Better Sleep'
                        },
                        {
                            text: 'Wake up Refreshed without Fatigue'
                        },
                        {
                            text: 'Designed for Easy Daily Use'
                        },
                        {
                            text: 'Supports with Jaw Dislocation Problem'
                        },
                        {
                            text: 'Safe and Comfortable, High Quality Materials'
                        },
                        {
                            text: 'Keeps airways open'
                        }
                    ],
                    weaknessList: [],
                    score: '9.5'

                },
                {
                    id: 4,
                    name: 'StopSnore Clip',
                    picture: require('../assets/image/snoring/silentSnore.png'),
                    link: 'https://hypertechx.com/ps/silentsnore/index.php?net=9785&aff={AFFID}&sid={SUBID}&cid={CLICKID}',
                    reviewLink: '',
                    buys: 586,
                    strengthList: [
                        
                        {
                            text: 'One-Size-Fits-All'
                        },
                        {
                            text: 'Soft & Light Design'
                        },
                        {
                            text: 'Stimulates The Sensory Nerves'
                        },
                        {
                            text: 'Non-Intrusive & Comfortable'
                        },
                        {
                            text: 'Made FromHigh-Quality & Non-Toxic Materials'
                        }
                    ],
                    weaknessList: [
                        {
                            text: 'Expensive For Value'
                        }
                    ],
                    score: '9.2'

                },
                {
                    id: 1,
                    name: 'SilentSnore',
                    picture: require('../assets/image/snoring/stopSnoreClip2.png'),
                    link: 'https://newxventions.com/intl_7/?prod=silentsnore&net=9785&aff={AFFID}&sid={SUBID}&cid={CLICKID}',
                    reviewLink: '',
                    buys: 586,
                    strengthList: [
                        {
                            text: 'Best Anti Snoring Device In The Market'
                        },
                        {
                            text: 'Eco-Friendly 100% Silicone Gel'
                        },
                        {
                            text: 'Super Easy To Use'
                        },
                        {
                            text: 'Solves Snoring Once And For All'
                        },
                        {
                            text: 'Easy To Clean And Reusable'
                        },
                        {
                            text: 'Helps Reduce Dry Mouth'
                        },
                        {
                            text: 'Extremely Low Price'
                        }
                    ],
                    weaknessList: [],
                    score: '10'

                }
            ]
        }
    },
    methods: {
    }

}
</script>

<style lang="less" scoped>
@import url('../assets/css/wifi-product.less');
</style>