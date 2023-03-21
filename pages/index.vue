<template>
    <div class="">
        <div class="clock">
        <p class="countdown">
            <span class="days">{{ days }}</span>Days
            <span class="hours">{{ hours }}</span>Hours
            <span class="minutes">{{ minutes }}</span>Minutes
            <span class="seconds">{{ seconds }}</span>Seconds
        </p>
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
  
  .countdown .days {
    color: rgb(250, 250, 255);
    background-color: black;
    border-radius: 40%;
    font-size: 135%;
  }

  .countdown .hours {
    color: rgb(250, 250, 255);
    background-color: black;
    border-radius: 40%;
    font-size: 135%;
  }
  
  .countdown .minutes {
    color: rgb(250, 250, 255);
    background-color: black;
    border-radius: 40%;
    font-size: 135%;
  }
  
  .countdown .seconds {
    color: rgb(250, 250, 255);
    background-color: black;
    border-radius: 40%;   
    font-size: 135%;
  }
  
  /* Resto de estilos */
  .container-form {
    background-color: rgb(255, 255, 255);
    width: 20%;
    height: 315px;
    text-align: center;
    margin-top: 154px;
    padding: 5%;
    border: solid 2px rgb(34, 145, 189);
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
  </style>