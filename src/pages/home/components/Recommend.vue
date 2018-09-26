<template>
    <div>

        <div class="recommend-title">
            热销推荐
        </div>
        <ul>
            <li class="item" v-for="item of recommendList" :key="item.id">
                <!--<div class="item-img-wrapper">-->
                    <img class="item-img" :src="item.imgUrl"/>
                <!--</div>-->
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>

    </div>
</template>

<script>
    export default {
        name: "recommend",
        data() {
            return{
                recommendList:[
                    {
                        id: '0001',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/1606/4a/4ae2bbafcc977a54e2.water.jpg_200x200_2724c6a1.jpg',
                        title:'合肥海洋世界',
                        desc:'合肥海洋世界很好玩合肥海洋世界很好玩合肥海洋世界很好玩'
                    },
                    {
                        id: '0002',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/1609/a9/a90f734bbc7b80aea3.water.jpg_200x200_fac101cb.jpg',
                        title:'合肥万达主题乐园',
                        desc:'合肥万达主题乐园合肥万达主题乐园合肥万达主题乐园合肥万达主题乐园'
                    },
                    {
                        id: '0003',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/201302/07/f01c7c672bf4ac39c8d65eac.jpg_200x200_56798fd8.jpg',
                        title:'紫微洞',
                        desc:'紫微洞紫微洞紫微洞紫微洞'
                    },
                    {
                        id: '0004',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/201405/21/8ef65ef070fed5e9509ca7c3541e3d1a.jpg_200x200_3afc0c15.jpg',
                        title:'姥山岛',
                        desc:'姥山岛姥山岛姥山岛姥山岛姥山岛姥山岛'
                    },
                    {
                        id: '0005',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/201402/18/3202d5679fa477beeb49635929b17dbe.jpg_200x200_5d61c58e.jpg',
                        title:'李鸿章故居',
                        desc:'李鸿章故居李鸿章故居李鸿章故居李鸿章故居李鸿章故居'
                    },
                    {
                        id: '0006',
                        imgUrl:'http://img1.qunarzz.com/sight/p0/1708/a3/a3d3dbf3c6a92fdfa3.water.jpg_200x200_bb0d483a.jpg',
                        title:'滨湖森林湿地公园',
                        desc:'滨湖森林湿地公园滨湖森林湿地公园滨湖森林湿地公园'
                    },
                ]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import "~styles/mixins.styl"
    .recommend-title
        margin-top .2rem
        line-height .8rem
        background #eee
        text-indent .2rem
    .item
        overflow hidden
        display flex
        height 1.9rem
        .item-img
            width 1.7rem
            height 1.7rem
            padding .1rem
        .item-info
            flex 1
            padding .1rem
            min-width 0
            .item-title
                line-height .54rem
                font-size .32rem
                ellipsis()
            .item-desc
                line-height .4rem
                color #ccc
                ellipsis()
            .item-button
                background #ff9300
                padding 0 .2rem
                border-radius .1rem
                color #fff
                line-height .44rem
                margin-top .16rem
                border none

</style>