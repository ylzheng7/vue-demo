<template>
    <div>
        <div class="search">
            <input class="search-input" type="text" placeholder="请输入城市名或拼音" v-model="keyword"/>
        </div>
        <div class="search-content" ref="searchList" v-show="keyword">
            <ul>
                <li class="search-item border-bottom-1px" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
                <li class="search-item border-bottom-1px" v-show="hasNoData"> 没有找到匹配数据 </li>
            </ul>
        </div>
    </div>

</template>

<script>

    import {mapMutations} from 'vuex'
    import Bscroll from 'better-scroll'

    export default {
        name: "CitySearch",
        props: {
            cities: Object
        },
        data() {
            return {
                keyword: '',
                timer: null,
                list: []
            }
        },
        computed: {
            hasNoData() {
                return !this.list.length
            }
        },
        watch: {
            keyword() {
                if (this.timer){
                    clearTimeout(this.timer)
                }
                if (!this.keyword){
                    this.list = [];
                    return;
                }
                this.timer = setInterval(()=>{
                    const result = [];
                    for(let i in this.cities){
                        this.cities[i].forEach(value => {
                            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1){
                                result.push(value)
                            }
                        });
                    }
                    this.list = result;
                },100);
            }
        },
        mounted() {
            this.scroll = new Bscroll(this.$refs.searchList)
        },
        methods: {
            handleCityClick(city) {
               this.changeCity(city)
                this.$router.push('/');
            },
            ...mapMutations(['changeCity'])
        }
    }
</script>

<style lang="stylus" scoped>

    @import "~styles/varibles.styl"

    .border-bottom-1px
        &:after
            background-color  #ccc

    .search
        height .72rem
        background-color $bgColor
        text-align center
        padding 0 .1rem
        .search-input
            box-sizing border-box
            height .62rem
            line-height .62rem
            width 100%
            border-radius  .06rem
            text-align center
            padding 0 .1rem
            color #666
    .search-content
        z-index 1
        overflow hidden
        position absolute
        top 1.58rem
        left 0
        right 0
        bottom 0
        background-color #eee
        .search-item
            background-color #fff
            padding .1rem .2rem

</style>