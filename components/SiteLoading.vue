<template>
    <div class="site-loading">
        <div class="lds-ring">
            <div />
            <div />
            <div />
            <div />
        </div>
    </div>
</template>

<script type="text/javascript">
export default {
    mounted() {
        this.$store.commit("SET_LOADING", true)
    },
    destroyed() {
        this.$store.commit("SET_LOADING", false)
    },
}
</script>

<style lang="scss">
// Pulled from https://loading.io/css/
.site-loading {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);

    .lds-ring {
        display: inline-block;
        position: relative;
        width: 64px;
        height: 64px;
    }
    .lds-ring div {
        box-sizing: border-box;
        display: block;
        position: absolute;
        width: 51px;
        height: 51px;
        margin: 6px;
        border: 6px solid var(--color-loading);
        border-radius: 50%;
        animation: lds-ring 1.2s cubic-bezier(0.5, 0, 0.5, 1) infinite;
        border-color: var(--color-loading) transparent transparent transparent;
    }
    .lds-ring div:nth-child(1) {
        animation-delay: -0.45s;
    }
    .lds-ring div:nth-child(2) {
        animation-delay: -0.3s;
    }
    .lds-ring div:nth-child(3) {
        animation-delay: -0.15s;
    }
    @keyframes lds-ring {
        0% {
            transform: rotate(0deg);
        }
        100% {
            transform: rotate(360deg);
        }
    }
}
</style>
