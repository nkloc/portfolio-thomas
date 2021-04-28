<template>
    <header :class="{ active: burgerMenuActive}">
        <div>
            <img src="../assets/logo.svg" alt="Logo d'odissey sécurité privée">
        </div>
        <div>
            <i @click.prevent="showMenu()" v-if="windowWidth < 749 && !burgerMenuActive" class="fas fa-bars burger"></i>
            <i @click.prevent="showMenu()" v-if="windowWidth < 749 && burgerMenuActive" class="fas fa-times burger"></i>
            <div v-if="windowWidth > 748 || burgerMenuActive" class="menu-mobile">
                <ul> 
                    <li> <a href="">Projects</a></li>
                    <li> <a href="">About me</a></li>
                    <li> <a href="">Contact</a></li>
                </ul>
            </div>

        </div>
    </header>
</template>

<style lang="stylus" scoped>
@import '../css/variables'

header 
    display flex
    align-items center
    height 80px
    background white
    justify-content space-between
    padding 0 50px
    div
        display flex
        align-items center

h1
    font-size 32px
    font-weight black
    text-align center
    span 
        position absolute
        font-size 12px
        font-weight regular
        color $nightblue-color
img 
    height 50px
    margin-right 15px

ul
    list-style-type none
    padding 0
    @media mobile
        display flex
        flex-direction column
        align-items center
        justify-content center
        width 100%

.menu-mobile
    @media mobile 
        position fixed 
        left 0
        top 80px
        width 100%
        background $black-color
        height calc(100vh - 80px)
        

li
    display inline-block
    margin 0 10px
    @media mobile 
        margin 40px 0


a
    color $gray-color
    text-decoration none 
    font-weight 500
    font-size 14px
    &:hover
        text-decoration underline
    @media mobile 
        color $white-color
        font-size 45px
        font-weight bold
        text-transform uppercase
        &:hover
            text-decoration none

.burger
    font-size 20px

.active 
    position fixed
    width calc(100% - 100px)
</style>

<script>
export default {
    data() {
        return {
            windowWidth: 0,
            burgerMenuActive: false,
        }
    },

    mounted() {
        this.$nextTick(function() {
            window.addEventListener('resize', this.getWindowWidth);
            //Init
            this.getWindowWidth()
        })
    },

    methods: {
        getWindowWidth() {
            this.windowWidth = document.documentElement.clientWidth;
        },
        showMenu(){
            this.burgerMenuActive = !this.burgerMenuActive;
        }
    },

    beforeDestroy() {
        window.removeEventListener('resize', this.getWindowWidth);
        window.removeEventListener('resize', this.getWindowHeight);
    }
}
</script>