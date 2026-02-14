<!DOCTYPE html>
<html>
<head>
  <style>
    body { background: #ddd; margin: 0; height: 100vh; overflow: hidden; font-family: sans-serif; }
    .corazón { position: absolute; color: pink; font-size: 2em; animation: flotar 6s infinite; }
    @keyframes flotar { to { transform: translateY(-100vh); } }
    #pantalla { text-align: center; padding: 50px; }
    #foto { filter: grayscale(1); max-width: 300px; margin: 20px; }
    #carta { display: none; background: white; border: 3px dashed #ff69b4; padding: 20px; margin: 40px; border-radius: 8px; }
    .polaroid { border: 1px solid #ccc; padding: 10px; margin: 5px; display: inline-block; transform: rotate(3deg); }
  </style>
</head>
<body>
  <div id="pantalla">
    <img id="foto" src="pareja-mar.jpg" alt="Pareja">
    <input type="password" id="clave" placeholder="Ingresa clave">
    <button onclick="verificar()">Entrar</button>
  </div>

  <div id="carta">
    <p>0110 desbloqueado. Te quiero, Darlin.</p>
    <div class="polaroid">Foto 1: Ese beso en la playa.</div>
    <div class="polaroid">Foto 2: Tú riéndote en Arequipa.</div>
  </div>

  <script>
    let corazones = '';
    for(let i=0; i<20; i++) {
      let top = Math.random()*100, left = Math.random()*100;
      corazones += `<div class="corazón" style="top:${top}%;left:${left}%;animation-delay:${Math.random()*5}s;">♥</div>`;
    }
    document.body.innerHTML += corazones;

    function verificar() {
      if(document.getElementById("clave").value === "0110") {
        document.getElementById("pantalla").style.display = "none";
        document.getElementById("carta").style.display = "block";
      }
    }
  </script>
</body>
</html>
