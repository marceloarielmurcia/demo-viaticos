# demo-viaticos
Demo funcional para Viaticos
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Demo Viajes</title>
<style>
body { font-family: Arial; background:#f4f6f9; padding:20px; }
.container { background:white; padding:20px; border-radius:10px; max-width:1000px; margin:auto; }
h2 { margin-top:20px; }

.fila { display:flex; gap:15px; margin-bottom:15px; }
.campo { flex:1; }

.label {
  background:#1F6091;
  color:white;
  padding:8px;
  text-align:center;
  border-radius:5px;
  margin-bottom:5px;
  font-size:13px;
}

input, select {
  width:100%;
  padding:8px;
  border-radius:5px;
  border:1px solid #ccc;
}

button {
  background:#4CAF50;
  color:white;
  border:none;
  padding:12px 30px;
  border-radius:6px;
  cursor:pointer;
  float:right;
}

.resumen {
  margin-top:20px;
  background:#eef6ff;
  padding:15px;
  display:none;
  white-space:pre;
}
</style>
</head>

<body>

<div class="container">

<h2>BUS</h2>
<div class="fila">
  <div class="campo">
    <div class="label">Adjuntar Pasaje</div>
    <input type="file" id="bus_pasaje">
  </div>
  <div class="campo">
    <div class="label">Empresa</div>
    <input type="text" id="bus_empresa">
  </div>
  <div class="campo">
    <div class="label">Costo</div>
    <input type="number" id="bus_costo">
  </div>
  <div class="campo">
    <div class="label">Forma de Pago</div>
    <select id="bus_pago">
      <option>TC Federico</option>
      <option>TC Tejerina</option>
      <option>Completar</option>
    </select>
  </div>
</div>

<h2>Aéreo</h2>
<div class="fila">
  <div class="campo">
    <div class="label">Código de Reserva</div>
    <input type="text" id="aer_codigo">
  </div>
  <div class="campo">
    <div class="label">Aerolínea</div>
    <input type="text" id="aer_línea">
  </div>
  <div class="campo">
    <div class="label">Costo</div>
    <input type="number" id="aer_costo">
  </div>
  <div class="campo">
    <div class="label">Forma de Pago</div>
    <select id="aer_pago">
      <option>TC Federico</option>
      <option>TC Tejerina</option>
      <option>Completar</option>
    </select>
  </div>
</div>

<h2>Alojamiento</h2>
<div class="fila">
  <div class="campo">
    <div class="label">Hotel</div>
    <input type="text" id="hotel">
  </div>
  <div class="campo"></div>
  <div class="campo">
    <div class="label">Costo</div>
    <input type="number" id="hotel_costo">
  </div>
  <div class="campo">
    <div class="label">Forma de Pago</div>
    <select id="hotel_pago">
      <option>TC Federico</option>
      <option>TC Tejerina</option>
      <option>Completar</option>
    </select>
  </div>
</div>

<button onclick="enviar()">Enviar</button>

<div id="resumen" class="resumen"></div>

</div>

<script>
function enviar(){
  let texto = "SOLICITUD DE VIAJE\n\n";

  texto += "BUS\n";
  texto += "Empresa: " + document.getElementById("bus_empresa").value + "\n";
  texto += "Costo: " + document.getElementById("bus_costo").value + "\n";
  texto += "Pago: " + document.getElementById("bus_pago").value + "\n\n";

  texto += "AEREO\n";
  texto += "Código: " + document.getElementById("aer_codigo").value + "\n";
  texto += "Aerolínea: " + document.getElementById("aer_línea").value + "\n";
  texto += "Costo: " + document.getElementById("aer_costo").value + "\n";
  texto += "Pago: " + document.getElementById("aer_pago").value + "\n\n";

  texto += "ALOJAMIENTO\n";
  texto += "Hotel: " + document.getElementById("hotel").value + "\n";
  texto += "Costo: " + document.getElementById("hotel_costo").value + "\n";
  texto += "Pago: " + document.getElementById("hotel_pago").value + "\n";

  document.getElementById("resumen").style.display = "block";
  document.getElementById("resumen").innerText = texto;
}
</script>

</body>
</html>
