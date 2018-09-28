<template>

        <div class="header">
            <router-link to="/">
                    <span class="iconfont header-back">&#xe624;</span>
            </router-link>
                城市选择

        </div>

</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style lang="stylus" scoped>

    @import "~styles/varibles.styl"

    .header
        position relative
        overflow hidden
        background-color $bgColor
        height  $headerHeight
        line-height  $headerHeight
        color #fff
        font-size .32rem
        text-align center
        .header-back
            position absolute
            top 0
            left 0
            width  .64rem
            text-align  center
            color #fff
</style>