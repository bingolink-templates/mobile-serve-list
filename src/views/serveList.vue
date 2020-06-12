<template>
    <div ref="wrap">
        <!-- 服务号消息列表 -->
        <div class="serve-list">
            <div class="news-list-title flex">
                <div class=" flex">
                    <bui-image class="mr20" src="/image/new.png" radius='17' width="34px" height="34px"></bui-image>
                    <text class="c0 f28 fw5 ml20">泊云客</text>
                </div>
                <text class="f26 c9" @click="serveMoreEvent">全部</text>
            </div>
            <div class="serve-list-content">
                <div class="content-item flex" v-for="(item,index) in serveList" :key='index' @click='serveListItemEvent(index)'>
                    <text class="f28 c0 w550 fw4 lines1">{{item}}</text>
                    <text class="f24 c153 fw4">03-04</text>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    var lapi = require('linkapi');
    export default {
        data() {
            return {
                serveList: ['品高云入围Forrest报告，妥妥的！', '魏明慧：公安行业部的行业云探索与实践', '纵享丝滑，聆客也可以！', '吴盈佳：政企行业的探索与实践']
            }
        },
        methods: {
            // 服务号更多
            serveMoreEvent() {
                this.$alert('服务更多')
            },
            // 服务号列表
            serveListItemEvent() {
                this.$alert('服务号列表')
            },
            broadcastWidgetHeight() {
                let _params = this.$getPageParams();
                setTimeout(() => {
                    dom.getComponentRect(this.$refs.wrap, (ret) => {
                        var channel = new BroadcastChannel('WidgetsMessage')
                        channel.postMessage({
                            widgetHeight: ret.size.height,
                            id: _params.id
                        });
                        channel.close();
                    });
                }, 100)
            }
        },
        mounted() {
            lapi.getLanguage((lang) => {
                this.$alert(lang);
            })
            this.broadcastWidgetHeight()
        }
    }
</script>

<style lang="css" src="../css/common.css"></style>
<style>
    .title-main {
        width: 150px;
    }

    .content-item {
        padding: 0 24px;
        height: 79px;
    }

    .news-list-title {
        padding: 19px 23px 19px 25px;
        height: 86px;
    }

    .news-list {
        background-color: #fff;
        border-radius: 10px;
        margin-bottom: 20px;
    }

    .serve-list {
        background-color: #fff;
        border-radius: 10px;
    }
</style>