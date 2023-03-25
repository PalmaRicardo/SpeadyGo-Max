<template>
  <div style="background-color: black; margin-top: -20px; height: 100vh">
    <div class="clock countdown">
      <div class="time-clock">{{ days }}</div>
      <div class="time-clock">{{ hours }}</div>
      <div class="time-clock">{{ minutes }}</div>
      <div class="time-clock">{{ seconds }}</div>
    </div>
    <div class="style-countdown">
      <p class="time" style="margin-right: -10px; margin-left: 37px">Days</p>
      <p class="time" style="margin-left: 43px; margin-right: 51px">Hours</p>
      <p class="time" style="margin-right: 76px; margin-left: -31px">Minutes</p>
      <p class="time" style="margin-left: -65px; margin-right: 20px">Seconds</p>
    </div>
    <div style="justify-content: flex-end; display: flex">
      <button class="open-modal" @click="showModal = true"></button>
    </div>
    <div class="container">
      <dialog style="position: absolute; z-index: 1" :open="showModal">
        <div class="container-form">
          <div class="figure"></div>
          <span class="form-title">Formulario</span>
          <form action="">
            <input type="text" class="all-put" id="nombre" name="nombre" placeholder="Nombre" required /><br />
            <input type="text" class="all-put" id="apellido" name="apellido" placeholder="Apellido" required /><br />
            <input type="email" class="all-put" name="email" id="email" placeholder="Correo Electronico" required /><br />
            <button type="submit" class="button-form">Enviar</button>
          </form>
        </div>
        <button @click="showModal = false">cerrar modal</button>
      </dialog>
      <client-only>
                    <vue-plyr :options="options">
                        <video controls crossorigin playsinline>
                            <source type="video/mp4" />
                        </video>
                    </vue-plyr>
                </client-only>
    </div>
    <div class="container-div"></div>
  </div>
</template>

<script>
import moment from "moment";
export default {
  data() {
    return {
      options: { quality: { default: '1080p' } },
      showModal: false,
      openingDate: "2023-04-01 12:00:00",
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
    };
  },
  created() {
    setInterval(() => {
      const now = moment();
      const opening = moment(this.openingDate);
      const duration = moment.duration(opening.diff(now));
      this.days = duration.days();
      this.hours = duration.hours();
      this.minutes = duration.minutes();
      this.seconds = duration.seconds();
    }, 1000);
  },
};
</script>

<style lang="css" scoped>
.plyr__poster {
  background-size: cover !important;
}

/* Estilos para el contador */
@font-face {
  font-family: "fuenteled";
  src: url(../pages/font/DS-DIGIT.TTF);
}

.open-modal {
  width: 100px;
  height: 100px;
  background-image: url("../components/images/mascota.png");
  background-repeat: no-repeat;
  border: none;
  outline: none;
  margin-right: 60px;
  position: absolute;
  z-index: 1;
}

.countdown {
  font-size: 24px;
  font-family: Arial, sans-serif;
  margin-top: 20px;
  text-align: center;
}

.countdown span {
  font-weight: bold;
}

.time-clock {
  color: #ffffff;
  background-color: rgb(4, 7, 27);
  border-radius: 30px;
  font-size: 35px;
  margin: 15px;
  width: 50px;
  height: 50px;
  text-align: center;
  align-items: center;
  display: grid;
  position: relative;
  border: 1px solid cyan;
  box-shadow: inset 0 0 10px 0 cyan;
  font-family: "fuenteled", sans-serif;
  margin-top: 10px;
}

/* Resto de estilos */
.container-form {
  background-color:rgba(0, 255, 255, 0.142);
  width: 315px;
  height: 350px;
  text-align: center;
  margin-top: 40px;
  padding: 5%;
  padding-top: 33px;
  border: solid 1px;
  border-color: cyan;
  border-radius: 5px;
  position: relative;
  display: block;
  justify-content: center;
}

.form-title {
  font-size: 25px;
  font-family: Arial, Helvetica, sans-serif;
  margin-bottom: 20px;
  font-weight: 600;
  color: white;
  text-shadow: 1px 0px 6px cyan;
  letter-spacing: 2px;
}

.container-div {
  display: flex;
  justify-content: center;
  position: relative;
}

.all-put {
  margin: 5%;
  width: 240px;
  height: 35px;
  border: none;
  background-color:rgba(0, 255, 255, 0.142);
  border-bottom: solid 2px cyan !important;
}

.button-form {
  border-radius: 30px;
  border: solid cyan;
  background-color: rgba(0, 255, 255,0.142);
  color: rgb(255, 255, 255);
  width: 88%;
  height: 35px;
  text-align: center;
  margin-top: 20px;
  font-size: 15px;
  font-weight: 600;
}

.clock {
  display: flex;
  justify-content: center;
  position: relative;
}

.style-countdown {
  display: flex;
  justify-content: center;
  margin-top: -18px;
}

.time {
  margin: 13px;
  color: cadetblue;
  font-weight: 900;
  font-size: 16px;
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
</style>
