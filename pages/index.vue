<template>
    <div style="background-color: black; margin-top: -20px; height: 100vh;">
        <div class="clock countdown">
            <div class="time-clock">{{ days }}</div>
            <div class="time-clock">{{ hours }}</div>
            <div class="time-clock">{{ minutes }}</div>
            <div class="time-clock">{{ seconds }}</div>
    </div>
    <div class="style-countdown">
    <p class="time" style="margin-right: -10px;margin-left: 37px;">Days</p>
    <p class="time" style="margin-left: 43px;margin-right: 51px;">Hours</p>
    <p class="time" style="margin-right: 76px;margin-left: -31px;">Minutes</p>
    <p class="time" style="margin-left: -65px;margin-right: 20px;">Seconds</p>
</div>
<div class="container-div">
    <div class="container-form">
        <h3 class="form">Formulario</h3>
        <form action="">
          <input type="text" class="all-put" id="nombre" name="nombre" placeholder="Nombre" required /><br>
          <input type="text" class="all-put" id="apellido" name="apellido" placeholder="Apellido" required /><br>
          <input type="email" class="all-put" name="email" id="email" placeholder="Correo Electronico" required /><br>
          <button type="submit" class="button-form">Enviar</button>
        </form>
      </div>
    </div>
    </div>
  </template>
  
  <script>
  import moment from 'moment';
  export default {
    data() {
      return {
        openingDate: '2023-04-01 12:00:00',
        days: 0,
        hours: 0,
        minutes: 0,
        seconds: 0
      }
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
    }
  }
  </script>
  
  <style lang="css" scoped>
  /* Estilos para el contador */
  @font-face {
        font-family: 'fuenteled';
        src: url(../pages/font/DS-DIGIT.TTF);
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
  .time-clock{
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
    font-family: 'fuenteled',sans-serif;
    margin-top: 120px;
    
  } 
  /* Resto de estilos */
  .container-form {
    background-color: rgb(255, 255, 255);
    width: 315px;
    height: 350px;
    text-align: center;
    margin-top: 40px;
    padding: 5%;
    padding-top: 33px;
    border: solid 3px rgb(34, 145, 189);
  }

  .form {
    font-size: 25px;
    font-family: Arial, Helvetica, sans-serif;
    margin-bottom: 20px;
    font-weight: 600;
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
    margin-left: -23px;
    border: none;
    border-bottom: solid 1px gray;
  }

  .button-form {
    background-color: rgb(0, 0, 0);
    color: rgb(255, 255, 255);
    border: none;
    width: 88%;
    height: 35px;
    text-align: center;
    margin-top: 20px;
  }
  .clock{
    display: flex;
    justify-content: center;
    position: relative;
  }
  .style-countdown{
    display: flex;
    justify-content: center;
    margin-top: -18px;
  }
  .time{
    margin: 13px;
    color: cadetblue;
    font-weight: 900;
    font-size: 16px;
  }
  </style>