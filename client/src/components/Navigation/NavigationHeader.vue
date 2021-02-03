<template>
    <div class="navigation-header">
        <nav class="main-nav">
            <a href="https://openbylaws.org.za/" class="header">
                <img src="../../assets/logo-md-inv.png" alt="open-bylaws-logo" />
                <span>Open By-laws</span>
            </a>
            <Burger v-bind:isPanelOpen="isPanelOpen" v-bind:closeSidebarPanel="closeSidebarPanel" />
        </nav>
        <div class="sidebar">
            <div class="sidebar-backdrop" v-on:click="closeSidebarPanel" v-if="isPanelOpen"></div>
            <transition name="slide">
                <div v-if="isPanelOpen" class="sidebar-panel">
                    <section v-on:click="closeSidebarPanel" class="close-burger-button">
                        <span class="close-burger-bar close-burger-bar--1"></span>
                        <span class="close-burger-bar close-burger-bar--2"></span>
                    </section>
                    <h2>Table of Contents</h2>
                    <ul class="chapter-list">
                        <li v-on:click="closeSidebarPanel" class="chapter" v-bind:key="chapter.id" v-for="chapter in chapters"><a :href="'#' + chapter.id">{{chapter.title}}</a></li>
                    </ul>
                </div>
            </transition>
        </div>
    </div>
</template>
<script>
import Burger from "./Burger";
import { chapterData } from '@/store.js';

export default {
    components: {
        Burger
    },
    data() {
        return {
            isPanelOpen: false,
            chapters: chapterData.contentList
        }
    },
    methods: {
        closeSidebarPanel() {
            this.isPanelOpen = !this.isPanelOpen
        }
    }
}
</script>
<style scoped>
    .navigation-header {
        display: none;
        background-color: #2F2B4A;
        position: fixed;
        top: 0;
        width: 100vw
    }
    .chapter-list {
        color: #F0F4F7;
        list-style-type: none;
        height: 100vh;
        margin-left: 10px;
    }
    .chapter {
        margin-bottom: 20px;
    }
    .chapter a {
        text-decoration: none;
        color: #F0F4F7;
    }
    .header {
        display: flex;
        height: 50px;
        text-decoration: none;
    }
    .header span {
        font-size: 20px;
        margin-left: 10px;
        margin-top: 10px;
        color: #F0F4F7;
    }
    .main-nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0.5rem 0.8rem;
        height: 70px;
    }
    .main-nav a {
        width: 220px;
    }
    @media screen and (max-width: 800px) {
        .navigation-header {
            display: block;
        }
    }
    .slide-enter-active,
    .slide-leave-active
    {
        transition: transform 0.2s ease;
    }

    .slide-enter,
    .slide-leave-to {
        transform: translateX(-100%);
        transition: all 100ms ease
    }

    .sidebar-backdrop {
        background-color: rgba(0,0,0,.5);
        width: 100vw;
        height: 100vh;
        position: fixed;
        top: 0;
        left: 0;
        cursor: pointer;
    }

    .sidebar-panel {
        background-color: #130f40;
        height: auto;
        position: fixed;
        left: 0;
        top: 0;
        z-index: 999;
        min-width: 200px;
        overflow-y: auto;
        padding : 30px 30px
    }
    h2 {
        color: #F0F4F7;
        margin-bottom: 40px;
        margin-left: 10px;
    }
    .sidebar-panel .contents-table {
        min-width: 200px;
    }
    .close-burger-button {
        position: relative;
        margin-left: 0;
        padding: 0;
        height: 30px;
        width: 32px;
        display: block;
        border: 0;
        border-radius: 0;
        background-color: transparent;
        pointer-events: all;
        margin-bottom: 40px;
    }
    .close-burger-bar {
        background-color: #F0F4F7;
        position: absolute;
        top: 50%;
        right: 6px;
        left: 6px;
        height: 2px;
        width: auto;
        margin-top: -1px;
        transform-origin: center;
    }
    .close-burger-bar--1 {
        transform: rotate(45deg)
    }
    .close-burger-bar--2 {
        transform: rotate(-45deg);
    }
</style>