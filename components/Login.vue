<template>
    <div class="lg:w-7/12 md:w-5/6 w-full mx-auto">
        <div class="border-1 border-[#333333] p-5 sm:p-[60px]">
            <form action="#">
                <div class="login-input-box">
                    <input type="text" name="user-name" placeholder="Correo" class="login-user">
                    <input type="password" name="user-password" placeholder="Contraseña" class="login-user">
                </div>
                <div class="login-toggle-btn">
                    <input class="mr-1" type="checkbox">
                    <label class="inline-block text-white" for="">Remember me</label>
                    <n-link class=" float-right text-[#ff0000] text-[14px]" to="/register">Forgot Password</n-link>
                </div>
                <div class="button-box">
                    <button class="buttone" type="submit">
                        <span>Login</span>
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>
<style lang="css">
.buttone{
    border-radius: 30px;
    border: solid cyan;
    padding: 10px 20px 13px;
    color: white;
}
.button-box{
    display: flex;
    justify-content: center;
}
.login-user{
    margin-bottom: 1.25rem;
    width: 100%;
    border-width: 1px;
    padding-left: 0.5rem;
    padding-right: 0.5rem;
    padding-top: 0.75rem;
    padding-bottom: 0.75rem;
    font-size: 14px;
    background-color: rgba(255, 0, 0, 0);
    border-bottom: solid 2px cyan !important;
    border: none;
}
</style>
<style lang="scss" scoped>
.user-input{
    @apply border-1 border-[#1e272d] text-white bg-[#1e272d] mb-5 px-2 py-3 w-full text-[14px];
}
</style>