<template>
    <div class="alert alert-primary">
        <h1>{{ title }}</h1>
        <p>{{ message }}</p>
        <button class="btn btn-primary mb-3" v-on:click="doAction">Show/Hide</button>
        <transition name="transit">
            <p v-if="flg" class="trans">Transition</p>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'Transform',
    data: function() {
        return {
            title: 'Trans&Anim',
            message: 'Transition Sample',
            flg: true,
            btn: 'Hide,'
        }
    },
    methods: {
        doAction() {
            this.flg = !this.flg
        },
    },
}
</script>

<style>
/* .transit-enter-active {
    transition: 1.0s;
} */
/* .transit-leave-active {
    transition: 1.0s;
    opacity: 0.5;
} */
/* .transit-enter, .transit-leave-to { */
    /* 平行移動
    transform: translateX(200px) translateY(-200px);
    opacity: 0.1; 
    */
    /* 拡大縮小     
    transform: scale(5.0);
    opacity: 0.1;
    */
    /* 回転 */
    /* transform: rotateZ(360deg);
    opacity: 0.1;
} */

/* キーフレームによるアニメーション */
.transit-leave-active {
    animation: anim 5.0s;
}
.transit-enter-active {
    animation: anim 2.5s reverse;
}
@keyframes anim {
    0% {
        transform: translateX(0px) translateY(0px) rotateZ(0deg);
        opacity: 1.0;
        background-color: #ddf;
    }
    25% {
        transform: translateX(250px) translateY(0px) rotateZ(0deg);
        opacity: 1.0;
        background-color: #fdd;
    }
    50% {
        transform: translateX(0px) translateY(-100px) rotateZ(540deg);
        opacity: 1.0;
        background-color: #dfd;
    }
    75% {
        transform: translateX(250px) translateY(-100px) rotateZ(540deg);
        opacity: 1.0;
        background-color: #fdf;
    }
    100% {
        transform: translateX(0px) translateY(-200px) rotateZ(1080deg);
        opacity: 0;
        background-color: #ffd;
    }
}
</style>