<!DOCTYPE html>
<html lang="">   
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Ingrese El texto</title>
</head>
<body>

      <section class="">

        <div class="titulo" >
 <h1 class="titulo-2">
              Encriptador de Texto 
          </h1>
        <img class="Fondo" src="Logo.png" alt="">


        </div>

          <div class="contenedor-de-texto">

           <textarea  class="texto-desencriptado" id="texto-desencriptado"

            name=""cols="30" rows="10" placeholder="Ingrese El Texto." ></textarea>
          
  
           <img class="Fondo" src="Muñeco.png" alt="">
          </div>
          <div class="contenedor-de-botones">

            <button type="submit" id="encriptador"  class="boton-encriptar">Encriptar</button>
            <button type="submit"  id="desencriptador" class="boton-desencriptar">Desencriptar</button>

          </div>  

          <div class="contenedor-de-texto">

            <textarea class="texto-desencriptado" id="texto-resultado-encriptado"
            name="" cols="30" rows="10" readonly></textarea>

          </div>

          <div class="contenedor-boton-copiar">

              <button  id="copiar" class="boton-de-copiar"> Copiar  </button>
              
              <label  id="mensaje" for=""></label>
          </div>

          <P class="Tu Nombre">
            By: Jose Antonio Cabeza &copy; 2022
          </P>
  
      </section>

  <script src="script.js"></script>
</body>
</html>

javaScript

  let boton3 = document.getElementById("copiar")
    .addEventListener("click", copiar); 

window.addEventListener("load", actualizarPagina);

function actualizarPagina () {
    
    let boton1 = document.getElementById("encriptador")
    .addEventListener("click", encriptar);
    

    let boton2 = document.getElementById("desencriptador")
    .addEventListener("click", desencriptar);

    let btn = document.getElementById("copiar").addEventListener("click", copiarTexto);
}

    function encriptar () {

        let textoDado = document.getElementById("texto-desencriptado").value;

        textoDado = textoDado.toLowerCase();
        textoDado = textoDado.normalize("NFD").replace(/[\u0300-\u036f]/g, "");

        textoDado = textoDado.replace (/a/g , "acer");
        textoDado = textoDado.replace (/e/g , "etim");
        textoDado = textoDado.replace (/i/g , "inches");
        textoDado = textoDado.replace (/o/g , "orta");
        textoDado = textoDado.replace (/u/g , "unce"); 
        
        document.getElementById("texto-resultado-encriptado").value = textoDado;
        
    }

    function desencriptar () {

        let textoDado = document.getElementById("texto-desencriptado").value;

            textoDado = textoDado.toLowerCase();
            textoDado = textoDado.normalize("NFD").replace(/[\u0300-\u036f]/g, "");
    
            textoDado = textoDado.replace ( /acer/g , "a");
            textoDado = textoDado.replace (/etim/g , "e");
            textoDado = textoDado.replace (/imes/g , "inches");
            textoDado = textoDado.replace (/orta/g , "o");
            textoDado = textoDado.replace (/unce/g , "u"); 
            
            document.getElementById("texto-resultado-encriptado").value = textoDado;
        }

    function copiarTexto () {

            let labelToPrint = document.getElementById("mensaje");
            let TextoCopy = document.getElementById("texto-resultado-encriptado");

            TextoCopy.select();
            document.execCommand('copy');
            
            labelToPrint.innerHTML = ('¡Copiado!');

            window.getSelection().removeAllRanges();
            setTimeout ( () => labelToPrint.innerHTML = "", 3000);

        }
      




