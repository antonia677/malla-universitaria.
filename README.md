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
  <h1>Malla Interactiva - Quinesiología</h1>
  <div class="grid-container">
    <div class="semestre">
      <h2>5° Semestre</h2>
      <div class="ramo" onclick="toggle('Principios de Enfermería')">Principios de Enfermería</div>
      <!-- más ramos... -->
    </div>
    <div class="semestre">
      <h2>6° Semestre</h2>
      <div class="ramo" onclick="toggle('Quinesiología Cardiorrespiratoria 1')">Quinesiología Cardiorrespiratoria 1</div>
      <!-- más ramos... -->
    </div>
    <!-- Agrega más semestres aquí -->
  </div>

  <script src="script.js"></script>
</body>
</html>

body {
  font-family: Arial, sans-serif;
  background: #f4f4f4;
  padding: 20px;
  color: #333;
}

h1 { text-align: center; margin-bottom: 30px; }
.grid-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 20px;
}
.semestre {
  background: #fff;
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 15px;
}
.semestre h2 {
  margin-top: 0;
  color: #005a9c;
}

.ramo {
  margin: 6px 0;
  padding: 8px;
  border: 1px solid #bbb;
  border-radius: 4px;
  cursor: pointer;
  transition: 0.2s;
}
.ramo:hover { background: #eaeaea; }
.ramo.aprobado {
  background: #c6f7d0;
  border-color: #4caf50;
  text-decoration: line-through;
}

const ramos = [
  "Principios de Enfermería", "Patología Cardiorrespiratoria",
  "Neurología Clínica", "Análisis de Movimiento 2",
  "Fisiología del Esfuerzo", "Traumatología y Ortopedia",
  "Salud Pública y Epidemiología", "Biostatística",
  "Semiología y Quinésica", "Biomecánica Ocupacional y Antropometría",
  "Quinesiología Traumatológica 1", "Ciclo Vital",
  "Quinesiología Cardiorrespiratoria 1", "Psicomotricidad",
  "Farmacología Aplicada a la Quinesiología", "Fisioterapia",
  "Quinesiología Traumática 2", "Práctica Intermedia 1"
];

// Al cargar, aplicar estado guardado
document.addEventListener('DOMContentLoaded', () => {
  ramos.forEach(nombre => {
    const elemento = Array.from(document.querySelectorAll('.ramo'))
      .find(el => el.textContent.trim() === nombre);
    if (elemento && localStorage.getItem(nombre) === 'true') {
      elemento.classList.add('aprobado');
    }
  });
});

function toggle(nombre) {
  const element = Array.from(document.querySelectorAll('.ramo'))
    .find(el => el.textContent.trim() === nombre);
  if (!element) return;
  const isAprobado = element.classList.toggle('aprobado');
  localStorage.setItem(nombre, isAprobado);
}
