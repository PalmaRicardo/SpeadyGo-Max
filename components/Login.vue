<template>
    <div style="justify-content: flex-start;display: flex;">
      <div class="card p-5 sm:p-[60px]">
        <br>
        <div class="figure"></div>
        <span class="text-login">INICIAR SESION</span>
        <form v-on:submit.prevent="validateForm">
          <div class="login-input-box">
            <input type="email" name="user-name" placeholder="Correo" class="login-user" v-model="email">
            <input type="password" name="user-password" placeholder="Contraseña" class="login-user" v-model="password">
          </div>
          <div class="login-toggle-btn">
            <input class="mr-1" type="checkbox">
            <label class="inline-block text-white" for="">Remember me</label>
            <n-link class="float-right" to="/register">¿Olvidaste tu contraseña?</n-link>
          </div>
          <div class="button-box">
            <button class="buttone" type="submit">
              <span>Login</span>
            </button>
          </div>
        </form>
        <div class="register-link">
          <p>¿Aún no tienes una cuenta en</p>
          <p style="margin-top: -22px;">SPEEDYGO MAX?</p>
        </div>
        <div class="button-box" style="margin-top: -24px;">
          <n-link to="/register" class="buttone">Suscribirse</n-link>
        </div>
      </div>
    </div>
  </template>
<style lang="css">
.buttone{
    margin-top: 10%;
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
    color: white;
}
.register-link{
    text-align: center;
    font-weight: 600;
    margin-top: 10%;
    color: white;
}
.card{
    border: solid 1px;
    border-color: cyan;
    border-radius: 5px;
    background-color: rgba(0, 255, 255, 0.142);
}
.figure{
    margin-top: 0;
    margin-bottom: 10%;
    width: 0px;
    height: 0px;
    border-width: 15px;
    border-style: solid;
    border-color: transparent transparent cyan cyan;
    transform: rotate(224deg);
}
.text-login {
    font-size: 30px;
    color: white;
    text-shadow: 1px 0px 6px cyan;
    letter-spacing: 2px;
    justify-content: center;
    display: flex;
    margin-top: -65px;
    margin-bottom: 50px;
}
.float-right{
    color: white;
}
</style>
<style lang="scss" scoped>
.user-input{
    @apply border-1 border-[#1e272d] text-white bg-[#1e272d] mb-5 px-2 py-3 w-full text-[14px];
}
</style>
<script>
import Swal from 'sweetalert2'

export default {
  data() {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    validateForm() {
      if (!this.email && !this.password) {
        Swal.fire({
          icon: 'error',
          title: 'Error...',
          text: 'Por favor ingrese su correo y contraseña',
        })
      } else if (!this.email) {
        Swal.fire({
          icon: 'error',
          title: 'Error...',
          text: 'Por favor ingrese su correo',
        })
      } else if (!this.password) {
        Swal.fire({
          icon: 'error',
          title: 'Error...',
          text: 'Por favor ingrese su contraseña',
        })
      } else {
        Swal.fire({
          title: 'Iniciando sesión...',
          icon: 'success',		
          showConfirmButton: false,
          timer: 1500
        }).then(() => {
          window.location.href = 'http://localhost:3000/home';
        });
      }
    }
  }
}
</script>