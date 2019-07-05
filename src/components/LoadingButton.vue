<template>
    <button :class="classNm" v-bind="{disabled : loading}" v-on:click.prevent="method">
        <span v-if="loading">요청중</span>
        <span v-if="!loading">{{title}}</span>
    </button>
</template>

<script>
    export default {
        name: "LoadingButton",
        props: {
            classNm: {
                type:String,
                required: false,
                default: 'btn'
            },
            title: {
                type: String,
                required: true
            },
            clickFunc: {
                type: Function,
                required: true
            },
            funcParam: [Object,String,Array]
        },
        data() {
            return {
                loading: false
            }
        },
        methods: {
            async method() {
                this.loading = true;
                this.funcParam ? await this.clickFunc(this.funcParam) : await this.clickFunc();
                this.loading = false;
            }
        }
    }
</script>

<style scoped>

</style>
