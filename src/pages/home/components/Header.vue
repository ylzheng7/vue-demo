<template>
    <div class="header">
        <div  class="header-left">
            <span class="iconfont">&#xe624;</span>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题
        </div>
        <router-link to="/City">
            <div class="header-right">
                {{this.city}}
                <span class="iconfont arrow_icon">&#xe613;</span>
            </div>
        </router-link>

    </div>
</template>

<script>
    import {mapState} from 'vuex'
    export default {
        name: "HomeHeader",
        computed: {
            ...mapState(['city'])
        },
    }
</script>

<style lang="stylus" scoped>
    @import "~styles/varibles.styl"

    .header
        line-height : $headerHeight
        display : flex
        background-color : $bgColor
        color : #fff
        .header-left
            width : .64rem
            float : left
            text-align : center
        .header-input
            flex : 1
            background-color : #ffffff
            border-radius : .1rem
            height :.64rem
            line-height : .64rem
            margin-top .12rem
            margin-left : .2rem
            margin-right : .2rem
            padding-left : .1rem
            padding-right : .1rem
            color: #ccc
            font-size : .3rem
        .header-right
            min-width : 1.04rem
            padding : 0 .1rem
            float right
            text-align center
            font-size : .3rem
            color #fff
        .arrow_icon
            font-size : .25rem
            margin-left : -.06rem
</style>