<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Carta de San Valentín</title>
  <a><link rel="stylesheet" href="./style.css"></a>
</head>
<body>


   

<div class="valentines-day">
  <div class="envelope"></div>
  <div class="heart"></div>
  <div class="text">HAPPY <br>VALENTINE'S <br>DAY!</div>
  <div class="front"></div>
</div>

<div id="card">
  <div class="side one"></div>
  <div class="side two">
    <h2>Mabel Olivera</h2>
    <p>Queridos programadores de todo el mundo</p>
    <p>En este día de San Valentín, quiero enviarles un mensaje especial para expresar mi profunda admiración por su increíble trabajo y dedicación. Cada línea de código que escriben es como una declaración de amor al mundo digital, cada algoritmo que diseñan es un poema de ingenio y creatividad.</p>
    <p>¡Feliz día de San Valentín, queridos programadores! Que sus corazones estén llenos de amor y sus líneas de código estén libres de bugs.</p>
  </div>
</div>

<script src='https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js'></script></body></html>


</body>
</html>


<script>
  $(document).ready(function(){
     
      $('.left-curtain').css('width', '0%');
      $('.right-curtain').css('width', '0%');
    
      $('.valentines-day').click(function(){
       
        $('.envelope').css({'animation':'fall 3s linear 1', '-webkit-animation':'fall 3s linear 1'});
        $('.envelope').fadeOut(800, function() {
       
          $('.valentines-day .heart, .valentines-day .text, .valentines-day .front').hide();
          
    
          $('#card').css({'visibility':'visible', 'opacity': 0, 'transform': 'scale(0.1)'});
          $('#card').animate({'opacity': 1}, {duration: 1000, step: function(now, fx) {
            var scale = 1 + Math.sin(now * Math.PI) * 0.1; 
            $(this).css('transform', 'scale(' + scale + ')');
          }});
        });
      });
    });
    
</script>


<style>

@import url('https://fonts.googleapis.com/css?family=Sacramento');

#card {
   height:500px;
   width:800px;
   margin:5em auto;
   position: fixed;
  top: -15px;
   left: 25%;
   display:flex;
   visibility:hidden;
}
#card h2 {
   font-size:3em;
   margin:0;
   color:pink;
   text-align: center;
}
#card p {
   font-size: 1.5em;
   text-align: justify;
   padding-left: 30px; 
   padding-right: 30px;
}


.side {
   background:#eee;
   height:550px;
   width:400px;

   padding:10px;
}
.side.one {
   width:320px;
   transform:skew(10deg,20deg);
   background:linear-gradient(90deg, #fff, #fff 40%, #ddd);
}
.side.two {
   transform:skew(10deg,-15deg);
   background:linear-gradient(-90deg, #fff, #fff 40%, #f0f0f0);
}

body {
   display: flex;
   align-items: center;
   justify-content: center;
   height: 100vh;
   font-family: 'Sacramento', cursive;
   background-color: #f1e3d3;
   overflow: hidden;
 }
 
 .valentines-day {
   position: relative;
   cursor: pointer;
 }
 
 .envelope {
   position: relative;
   filter: drop-shadow(0 0 25px rgba(0,0,0,.3));
 }
 
 .envelope:before {
   content:"";
   position: absolute;
   width:254px;
   height:254px;
   background-color: #ff9494;
   transform: rotate(-45deg);
   border-radius: 0 15px 0 0;
   left:-37px;
   top:-82px;
 }
 
 .envelope:after {
   content:"";
   position: absolute;
   background-color: #ff9494;
   width:360px;
   height:225px;
   left:-90px;
   top:45px;
 }
 
 .heart {
   position: relative;
   background-color: #e01911;
   display: inline-block;
   height: 180px;
   top:50px;
   left:0;
   transform: rotate(-45deg);
   width:180px;
   filter: drop-shadow(0 -10px 25px rgba(0,0,0,.3));
   transition: .5s;
 }
   
 .heart:before, .heart:after {
   content:"";
   background-color: #e01911;
   border-radius:50%;
   height: 180px;
   width: 180px;
   position: absolute;
   }
   
 .heart:before {
   top:-100px;
   left:0;}
   
 .heart:after {
   left:100px;
   top:0;}
 
 .front {
   position: absolute;
   width:0;
   height:0;
   border-right: 190px solid #fbd2d2;
   border-top: 113px solid transparent;
   border-bottom: 113px solid transparent;
   top:44px;
   left:80px;
   z-index:4;
 }
 
 .front:before {
   content:"";
   position: absolute;
   width:0;
   height:0;
   border-left: 190px solid #fbd2d2;
   border-top: 113px solid transparent;
   border-bottom: 113px solid transparent;
   top:-113px;
   left:-170px;
 }
 
 .front:after {
   width:0;
   height:0;
   position: absolute;
   content:"";
   border-bottom: 150px solid #fce7e9;
   border-right:180px solid transparent;
   border-left: 180px solid transparent;
   top:-36px;
   left:-170px;
 }
 
 .text {
   position: absolute;
   font-family: arial;
   letter-spacing:5px;
   text-align: center;
   color: white;
   z-index:2;
   top:80px;
   left:15px;
   transition: .5s;
 }
 
 .valentines-day:hover .heart {
   transform: translateY(-50px) rotate(-45deg);
 }
 
 .valentines-day:hover .text {
   transform: translateY(-50px);
 }
 

</style>
