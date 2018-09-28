<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <!-- slides -->
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swipe-img" :src="item.imgUrl"/>
            </swiper-slide>
            <!-- Optional controls -->
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>

</template>

<script>
    export default {
        name: "HomeSwiper",
        props: {
            list:Array
        },
        data() {
            return {
                changeColor: {},
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true,
                    autoplay: true
                },
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