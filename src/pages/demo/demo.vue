<template>
    <div class="w-full max-w-screen-sm h-full mx-auto px-10 py-10">
        <div class="m-4 flex flex-row justify-center items-center">
            <h1 class="text-2xl font-bold">Demo Page</h1>
        </div>
        <div class="m-4 flex flex-row justify-center items-center">
            <p class="text-lg">这是一个演示页面，展示了按钮、输入框和卡片组件的使用。</p>
        </div>
        <div class="m-4 flex flex-row justify-center items-center">
            <!-- 主题切换按钮 -->
            <label class="swap swap-rotate">
                <!-- this hidden checkbox controls the state -->
                <input type="checkbox" class="theme-controller" value="night" />
                <!-- sun icon -->
                <svg class="swap-off h-10 w-10 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path
                        d="M5.64,17l-.71.71a1,1,0,0,0,0,1.41,1,1,0,0,0,1.41,0l.71-.71A1,1,0,0,0,5.64,17ZM5,12a1,1,0,0,0-1-1H3a1,1,0,0,0,0,2H4A1,1,0,0,0,5,12Zm7-7a1,1,0,0,0,1-1V3a1,1,0,0,0-2,0V4A1,1,0,0,0,12,5ZM5.64,7.05a1,1,0,0,0,.7.29,1,1,0,0,0,.71-.29,1,1,0,0,0,0-1.41l-.71-.71A1,1,0,0,0,4.93,6.34Zm12,.29a1,1,0,0,0,.7-.29l.71-.71a1,1,0,1,0-1.41-1.41L17,5.64a1,1,0,0,0,0,1.41A1,1,0,0,0,17.66,7.34ZM21,11H20a1,1,0,0,0,0,2h1a1,1,0,0,0,0-2Zm-9,8a1,1,0,0,0-1,1v1a1,1,0,0,0,2,0V20A1,1,0,0,0,12,19ZM18.36,17A1,1,0,0,0,17,18.36l.71.71a1,1,0,0,0,1.41,0,1,1,0,0,0,0-1.41ZM12,6.5A5.5,5.5,0,1,0,17.5,12,5.51,5.51,0,0,0,12,6.5Zm0,9A3.5,3.5,0,1,1,15.5,12,3.5,3.5,0,0,1,12,15.5Z" />
                </svg>
                <!-- moon icon -->
                <svg class="swap-on h-10 w-10 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
                    <path d="M21.64,13a1,1,0,0,0-1.05-.14,8.05,8.05,0,0,1-3.37.73A8.15,8.15,0,0,1,9.08,5.49a8.59,8.59,0,0,1,.25-2A1,1,0,0,0,8,2.36,10.14,10.14,0,1,0,22,14.05,1,1,0,0,0,21.64,13Zm-9.5,6.69A8.14,8.14,0,0,1,7.08,5.22v.27A10.15,10.15,0,0,0,17.22,15.63a9.79,9.79,0,0,0,2.1-.22A8.11,8.11,0,0,1,12.14,19.73Z" />
                </svg>
            </label>
        </div>
        <div class="m-4 flex flex-row flex-wrap justify-center items-center gap-2">
            <button class="btn btn-neutral">Neutral</button>
            <button class="btn btn-primary">Primary</button>
            <button class="btn btn-secondary">Secondary</button>
            <button class="btn btn-accent">Accent</button>
            <button class="btn btn-info">Info</button>
            <button class="btn btn-success">Success</button>
            <button class="btn btn-warning">Warning</button>
            <button class="btn btn-error">Error</button>
        </div>
        <div class="m-4 flex flex-row flex-wrap justify-center items-center gap-2">
            <button class="btn btn-soft">Default</button>
            <button class="btn btn-soft btn-primary">Primary</button>
            <button class="btn btn-soft btn-secondary">Secondary</button>
            <button class="btn btn-soft btn-accent">Accent</button>
            <button class="btn btn-soft btn-info">Info</button>
            <button class="btn btn-soft btn-success">Success</button>
            <button class="btn btn-soft btn-warning">Warning</button>
            <button class="btn btn-soft btn-error">Error</button>
        </div>
        <div class="m-4 flex flex-col flex-wrap justify-center items-center gap-2">
            <input type="text" placeholder="请输入姓名" class="input" v-model="userName" />
            <input type="text" placeholder="请输入邮箱" class="input" v-model="userMail" />
            <button class="btn btn-wide btn-soft btn-secondary" @click="summit()">
                <font-awesome-icon icon="fa-solid fa-heart" />
                提交
            </button>
        </div>
        <div class="m-4 flex flex-col flex-wrap justify-center items-center gap-2" :class="isShow ? 'block' : 'hidden'">
            <div class="card w-96 bg-base-100 card-md shadow-sm">
                <div class="card-body">
                    <h2 class="card-title">尊敬的 {{ userName }}</h2>
                    <p>你的邮件地址是 {{ userMail }}</p>
                    <div class="justify-end card-actions">
                        <button class="btn btn-primary" @click="confirm()">我已知晓</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DemoPage',
    components: {},
    setup() {
        return {};
    },
    data() {
        return {
            synthwave: 'night',
            isShow: false,
            userName: null,
            userMail: null
        };
    },
    created() {},
    mounted() {},
    updated() {},
    methods: {
        // 提交按钮
        async summit() {
            this.isShow = true;
        },
        // 确认按钮
        async confirm() {
            this.isShow = false;
        }
    }
};
</script>

<style scoped></style>
