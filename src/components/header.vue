<template lang="html">
<header>
    <div class="page-cover" v-show='this.showMenu' @click='closeMenu'>

    </div>
    <nav class="menu" :class="{'showMenu':showMenu}">

    </nav>
    <div class="header-content" :class="{'h-content-hide':showMenu}">
        <icon name="bars" scale='1.5' @click.native="openMenu"></icon>
        <span>全部</span>
        <icon name='user' scale='1.5'></icon>
    </div>
</header>
</template>

<script>
export default {
    data() {
        return {
            showMenu: false,
        };
    },
    methods: {
        openMenu() {
            this.showMenu = true;
        },
        closeMenu() {
            this.showMenu = false;
        },
    },
};
</script>

<style lang="scss">
.header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-sizing: border-box;
    font-size: 16px;
    padding: 10px 20px;
    box-shadow: 0 0 4px rgba(0,0,0,.25);
    transition: transform 0.5s;
}
.h-content-hide {
    transform: translate3d(200px,0,0);
}
.page-cover {
    position: absolute;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,.4);
    z-index: 2;
}
.menu {
    position: absolute;
    z-index: 3;
    width: 200px;
    height: 100%;
    background-color: #fff;
    transform: translate3d(-200px,0,0);
    transition: transform 0.5s;
}
.showMenu {
    transform: translate3d(0,0,0);
}
</style>
