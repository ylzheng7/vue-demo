<template>

    <div class="list" ref="wrapper">
        <div>
            <div class="area">
                <div class="title">当前城市</div>
                <div class="btn-list">
                    <div class="btn-wrapper">
                        <div class="btn">北京</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title " >热门城市</div>
                <div class="btn-list">
                    <div class="btn-wrapper"v-for="item of hotCities" :key="item.id">
                        <div class="btn">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
                <div class="title ">{{key}}</div>
                <div class="item-list" >
                    <div class="item border-bottom-1px" v-for="innerItem of item" :key="innerItem.id">
                        {{innerItem.name}}
                    </div>
                </div>
            </div>

        </div>
    </div>
    
</template>

<script>
    import Bscroll from 'better-scroll'
    export default {
        name: "CityList",
        props:{
            cities: Object,
            hotCities: Array,
            letter: String
        },
        watch: {
            letter() {
                if (this.letter){
                    const element = this.$refs[this.letter][0];
                    this.scroll.scrollToElement(element);
                }
            }
        },
        mounted() {
            this.scroll = new Bscroll(this.$refs.wrapper)
        },
        methods: {

        }
    }
</script>

<style lang="stylus" scoped>

    .border-bottom-1px
        /*&:before*/
            /*background-color  #ccc*/
        &:after
            background-color  #ccc
    .border-top-1px
        &:before
            background-color  #ccc
        /*&:after*/
            /*background-color  #ccc*/

    .list
        overflow hidden
        position absolute
        top 1.58rem
        left 0
        right  0
        bottom 0
        .title
            line-height .54rem
            background-color #eee
            padding-left .2rem
            color #666
            font-size .26rem
        .btn-list
            overflow hidden
            padding .1rem .6rem .1rem .1rem
            .btn-wrapper
                float left
                width 33.33%
                .btn
                    padding .1rem 0
                    text-align center
                    margin .1rem
                    border .02rem solid #ccc
                    border-radius .06rem
        .item-list
            .item
                padding-left  .2rem
                line-height .54rem
                color #666
</style>