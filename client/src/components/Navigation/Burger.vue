<template>
    <div id="burger" v-on:click="toggle">
        <slot>
            <button type="button" class="burger-button" title="Menu">
                <span class="burger-bar burger-bar--1"></span>
                <span class="burger-bar burger-bar--2"></span>
                <span class="burger-bar burger-bar--3"></span>
            </button>
        </slot>
    </div>
</template>
<script>
    
    export default {
        name: "Burger",
        props: [ "closeSidebarPanel"],
        methods: {
            toggle() {
                this.closeSidebarPanel()
            }
        }
    }
</script>
<style>
    button {
        cursor: pointer;
    }
    button:focus {
        outline: 0;
    }
    .burger-button {
        position: relative;
        height: 30px;
        width: 32px;
        display: block;
        z-index: 999;
        border: 0;
        border-radius: 0;
        background-color: transparent;
        pointer-events: all;
        transition: transform .6s cubic-bezier(.165,.84,.44,1);
    }
    .burger-bar {
        background-color: #F0F4F7;
        position: absolute;
        top: 50%;
        right: 6px;
        left: 6px;
        height: 2px;
        width: auto;
        margin-top: -1px;
    }
    .burger-bar--1 {
        -webkit-transform: translateY(-6px);
        transform: translateY(-6px);
    }
    .burger-bar--2 {
        transform-origin: 100% 50%;
        transform: scaleX(.8);
    }
    .burger-bar--3 {
        transform: translateY(6px);
    }
</style>