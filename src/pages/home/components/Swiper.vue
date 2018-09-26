<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swipe-img" :src="item.imgUrl"/>
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>s
        </swiper>
    </div>

</template>s

<script>
    export default {
        name: "HomeSwiper",
        data() {
            return {
                changeColor: {},
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true
                },
                swiperList:[
                    {
                        id: '0001',
                        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1808/f4/5f2289f8675f0502.jpg_750x200_ab1633c7.jpg'
                    },{
                        id: '0002',
                        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
                    },{
                        id: '0003',
                        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/50/670c61165170f902.jpg_750x200_c4b8d1dc.jpg'
                    },{
                        id: '0004',
                        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1809/ad/50e124f6caef1e02.jpg_750x200_2bec926d.jpg'
                    }
                ]
            }
        }
    }
</script>

<style lang="stylus" scoped>

    .wrapper >>> .swiper-pagination-bullet-active
                     background: #fff
    .wrapper
        overflow :hidden
        width:100%
        height:0
        padding-bottom : 26.66%
        background-color : #eee
        .swipe-img
            width:100%
</style>