<template>
    <div style="flex:1">
        <serveList></serveList>
    </div>
</template>

<!--引入bui-weex样式文件-->
<style lang="scss" src="bui-weex/src/css/buiweex.scss"></style>

<script>
    import serveList from "./serveList.vue";
    module.exports = {
        data () {
            return {}
        },
        components: {
          serveList
        }
    }
</script>