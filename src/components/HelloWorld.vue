<template>

    <div>

        <div class="container" v-for="(item,index) in testData">
            <div class="test" :class="{new: item.isActived}" @click="changeColor(item)">{{ index +":"+ item.content }}
            </div>
        </div>

    </div>

</template>

<script>
    import Vue from 'vue'

    export default {
        name: 'HelloWorld',
        data() {
            return {
                testData: [
                    {
                        id: '0001',
                        content: '未选择'
                    },
                    {
                        id: '0002',
                        content: '未选择'
                    },
                    {
                        id: '0003',
                        content: '未选择'
                    }
                    , {
                        id: '0004',
                        content: '未选择'
                    }
                    , {
                        id: '0005',
                        content: '未选择'
                    }
                ]
            }
        },

        mounted() {

        },
        methods: {
            changeColor(item) {
                var self = this;
                console.log(item)
                if (item.isActived === true) {
                    item.isActived = false
                    item.content = "未选择"
                } else {
                    item.isActived = true
                    item.content = "已选择"
                }
            }
        }
    }
</script>

<style lang="stylus" scoped>

    .container
        width 100%
        height 100%
        .test
            margin-top 5px
            width 100%
            height 40px
            line-height 40px
            vertical-align middle
            background cadetblue
            text-align center
            color #fff
        .new
            background black

</style>
