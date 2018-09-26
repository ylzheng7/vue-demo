<template>
    <div>

        <div class="weekend-title">
            周末去哪儿
        </div>
        <ul>
            <li class="item" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl"/>
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>

    </div>
</template>

<script>
    export default {
        name: "weekend",
        data() {
            return{
                recommendList:[
                    {
                        id: '0001',
                        imgUrl:'http://img1.qunarzz.com/sight/source/1505/94/23202a6a5864d8.jpg_r_640x214_92f21625.jpg',
                        title:'合肥必游TOP5',
                        desc:'尽览名胜旖旎风光，到古迹吊古凭今'
                    },
                    {
                        id: '0002',
                        imgUrl:'http://img1.qunarzz.com/sight/source/1505/8b/c2fd277d149df.jpg_r_640x214_81b57b6a.jpg',
                        title:'醉美历史古韵',
                        desc:'千年的风雨，赋予了这里深厚的历史积淀'
                    },
                    {
                        id: '0003',
                        imgUrl:'http://img1.qunarzz.com/sight/source/1511/fd/0285e145e82233.jpg_r_640x214_b5f10121.jpg',
                        title:'黟县旅游',
                        desc:'走进黄山，探寻桃花源里的人家'
                    },
                    {
                        id: '0004',
                        imgUrl:'http://img1.qunarzz.com/sight/source/1505/b7/0f18d39e7abfbd.jpg_r_640x214_62749f2c.jpg',
                        title:'齐享户外自然美景',
                        desc:'若想感受纯粹的自然，不妨市郊游湖登山'
                    }
                ]
            }
        }
    }
</script>

<style lang="stylus" scoped>
    @import "~styles/mixins.styl"
    .weekend-title
        margin-top .2rem
        line-height .8rem
        background #eee
        text-indent .2rem
    .item-img-wrapper
        overflow hidden
        height 0
        padding-bottom 34%
        .item-img
            width 100%
    .item-info
        padding .1rem
        margin-bottom .2rem
        .item-title
            line-height .54rem
            font-size .32rem
            ellipsis()
        .item-desc
            line-height .4rem
            color #ccc
            ellipsis()


</style>