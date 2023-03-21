<template>
    <div>
        <OffcanvasSidebar :class="{'show-mobile-menu' : navOpen}" @togglenav="navOpen = !navOpen" />
        <div class="py-[50px] md:py-[80px] bg-[#000000]" style="height: 760px;">
            <div class="container">
                <Login />
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        components: {
            MainHeader: () => import('@/components/header/MainHeader'),
            OffcanvasSidebar: () => import('@/components/header/OffcanvasSidebar'),
            Breadcrumb: () => import('@/components/Breadcrumb'),
            Login: () => import('@/components/Login'),
            FooterTop: () => import('@/components/footer/FooterTop'),
            FooterBottom: () => import('@/components/footer/FooterBottom')
        },
        data () {
            return {
                navOpen: false
            }
        }
    }
</script>
<style lang='scss'>
.login-register-tab{
    & .nuxt-link-exact-active{
        @apply text-[#f4181c];
    }
}
</style>