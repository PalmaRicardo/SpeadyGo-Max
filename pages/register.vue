<template>
    <div>
        <div class="py-[50px] md:py-[80px] bg-[#000000]">
            <div class="container">
                <div class="flex items-center justify-center text-center login-register-tab mb-8 md:mb-[60px]">
                    <n-link to="/login" class="text-white text-[25px] font-bold mr-5 pr-5 relative hover:text-[#f4181c] before:content-[''] before:bg-[#454545] before:h-[18px] before:mx-auto before:absolute before:-right-[2px] before:top-[3px] before:transition-all before:w-[1px]">Login</n-link>
                </div>
                <Register />
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        components: {
        },
        data () {
            return {
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