<template>
    <div style="background-color: black; margin-top: -20px; height: 100vh;">
        <div class="clock countdown">
            <div class="time-clock">{{ days }}</div>
            <div class="time-clock">{{ hours }}</div>
            <div class="time-clock">{{ minutes }}</div>
            <div class="time-clock">{{ seconds }}</div>
    </div>
    <div class="style-countdown">
    <p class="time">Days</p>
    <p class="time">Hours</p>
    <p class="time">Minutes</p>
    <p class="time">Seconds</p>
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
    color: rgb(48, 88, 107);
    background-color: rgb(4, 7, 27);
    border-radius: 87%;
    border: solid 2px rgb(201, 188, 3);
    font-size: 135%;
    margin: 15px;
    width: 4%;
    height: 50px;
    text-align: center;
    align-items: center;
    display: grid;
    position: relative;
  } 
  /* Resto de estilos */
  .container-form {
    background-color: rgb(255, 255, 255);
    width: 20%;
    height: 315px;
    text-align: center;
    margin-top: 100px;
    padding: 5%;
    border: solid 3px rgb(34, 145, 189);
  }

  .form {
    font-size: 25px;
    font-family: Arial, Helvetica, sans-serif;
    margin-top: -40px;
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
    width: 138%;
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
    margin-left: 35px;
    margin-right: 7px;
    margin-top: -18px;
  }
  .time{
    margin: 13px;
    color: cadetblue;
    font-weight: 900;
    font-size: 16px;
  }
  </style>