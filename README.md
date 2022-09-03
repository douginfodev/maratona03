# maratona03
#PROGRAMAÇÂO CONTINUADA: Projeto Rocketcoffee criado durante a semana da Maratona Explorer 3.0 realizada pela Rocketseat.


document.addEventListener("DOMContentLoaded", function(){

   var url1 = "../css/estiloprincipal.css";
   var url2 = "../css/estiloprincipal_acessibilidade.css";
   var botao = document.getElementById("botao_acess");

   var css = localStorage.getItem("css");
   if(!css){
      criaTag(url1);
   }else{
      if(css == url2){
         botao.value = 2;
         botao.textContent = "ON";
      }
      criaTag(css);
   }

   function criaTag(url){
      var estilo = document.createElement("link");
      estilo.rel = "stylesheet";
      estilo.type = "text/css";
      estilo.className = "acess";
      estilo.href = url;
      document.body.appendChild(estilo);
   }

   botao.onclick = function(){

      var tag = document.getElementsByClassName("acess");

      if(this.value == 1){
         this.textContent = "ON";
         this.value = 2;
         tag[0].href = url2;
         localStorage.setItem("css", url2);
      }else{
         this.textContent = "OFF";
         this.value = 1;
         tag[0].href = url1;
         localStorage.setItem("css", url1);
      }

   }

});
