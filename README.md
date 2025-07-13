# malla-universitaria.
malla interactiva de mis ramos universitarios 
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Malla Interactiva de Quinesiología</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Malla Interactiva - Quinto y Sexto Semestre</h1>

  <h2>Quinto Semestre</h2>
  <div class="malla">
    <div class="ramo" onclick="toggleAprobado(this)">Principios de Enfermería</div>
    <div class="ramo" onclick="toggleAprobado(this)">Patología Cardiorrespiratoria</div>
    <div class="ramo" onclick="toggleAprobado(this)">Neurología Clínica</div>
    <div class="ramo" onclick="toggleAprobado(this)">Análisis de Movimiento 2</div>
    <div class="ramo" onclick="toggleAprobado(this)">Fisiología del Esfuerzo</div>
    <div class="ramo" onclick="toggleAprobado(this)">Traumatología y Ortopedia</div>
    <div class="ramo" onclick="toggleAprobado(this)">Salud Pública y Epidemiología</div>
    <div class="ramo" onclick="toggleAprobado(this)">Biostatística</div>
    <div class="ramo" onclick="toggleAprobado(this)">Semiología y Quinésica</div>
    <div class="ramo" onclick="toggleAprobado(this)">Biomecánica Ocupacional y Antropometría</div>
    <div class="ramo" onclick="toggleAprobado(this)">Quinesiología Traumatológica 1</div>
    <div class="ramo" onclick="toggleAprobado(this)">Ciclo Vital</div>
  </div>

  <h2>Sexto Semestre</h2>
  <div class="malla">
    <div class="ramo" onclick="toggleAprobado(this)">Quinesiología Cardiorrespiratoria 1</div>
    <div class="ramo" onclick="toggleAprobado(this)">Psicomotricidad</div>
    <div class="ramo" onclick="toggleAprobado(this)">Farmacología Aplicada a la Quinesiología</div>
    <div class="ramo" onclick="toggleAprobado(this)">Fisioterapia</div>
    <div class="ramo" onclick="toggleAprobado(this)">Quinesiología Traumática 2</div>
    <div class="ramo" onclick="toggleAprobado(this)">Práctica Intermedia 1</div>
  </div>

  <script src="script.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  background-color: #f7f7f7;
  color: #333;
  text-align: center;
  padding: 30px;
}

h1 {
  font-size: 28px;
  margin-bottom: 10px;
}

h2 {
  margin-top: 40px;
  color: #0066cc;
}

.malla {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
  margin: 20px 0;
}

.ramo {
  background-color: white;
  padding: 15px;
  border: 2px solid #ddd;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.2s;
}

.ramo:hover {
  background-color: #e0e0e0;
}

.ramo.aprobado {
  background-color: #c9f5d2;
  border-color: #4caf50;
  text-decoration: line-through;
}
function toggleAprobado(element) {
  element.classList.toggle("aprobado");
}
