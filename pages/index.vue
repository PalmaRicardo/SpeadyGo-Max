<template>
<!--Formulario-->
<div class="container-div">
    <div class="container-form">
        <h3 class="form">Formulario</h3>
        <form action="">
            
            <input type="text" class="all-put" id="nombre" name="nombre"  placeholder="Nombre" required><br>
            <input type="text" class="all-put" id="apellido" name="apellido"  placeholder="Apellido" required><br>
            <input type="email" class="all-put" name="email" id="email" placeholder="Correo Electronico" required><br>
            <button type="submit" class="button-form">Enviar</button>
    
        </form>
    </div>
    </div>

    </template>
    <!--Estilos-->
    <style lang="css" scoped>
    .container-form{
        background-color: rgb(255, 255, 255);
        width: 20% ;
        height: 315px ;
        text-align: center;
        margin-top: 154px;
        padding: 5%;
        border: solid 2px rgb(34, 145, 189);
    }
    .form{
        font-size: 25px;
        font-family: Arial, Helvetica, sans-serif;
        margin-top: -40px;
        margin-bottom: 20px;
        font-weight: 600;
    }
    .container-div{
        display: flex;
        justify-content: center;
        position: relative;
    }
    .all-put{
        margin: 5%;
        width: 138%;
        height: 35px;
        margin-left: -23px;
        border: none;
        border-bottom: solid 1px gray;
    }
    .button-form{
        background-color: rgb(0, 0, 0);
        color: rgb(255, 255, 255);
        border: none;
        width: 88%;
        height: 35px;
        text-align: center;
        margin-top: 20px;
    }
    </style>