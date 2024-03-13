<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tabla de Posiciones</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }
        table {
            width: 80%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: center;
        }
        th {
            background-color: #4CAF50;
            color: white;
            font-weight: bold;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        caption {
            font-size: 1.5em;
            margin-bottom: 10px;
        }
    </style>
</head>
<body>
    <table id="tablaPosiciones">
        <caption>Tabla de Posiciones</caption>
        <thead>
            <tr>
                <th>Equipo</th>
                <th>Partidos Jugados</th>
                <th>Partidos Ganados</th>
                <th>Partidos Empatados</th>
                <th>Partidos Perdidos</th>
                <th>Puntos</th>
            </tr>
        </thead>
        <tbody>
             <tr>
                <td>Chivamamis</td>
                <td>4</td>
                <td>1</td>
                <td>2</td>
                <td>1</td>
                <td>0</td>
            </tr>
            <tr>
                <td>Tiburonas</td>
                <td>3</td>
                <td>3</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
      
            <tr>
                <td>Winx</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>2</td>
            </tr>
<tr>
                <td>Chelsea</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>Charritas</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>spurs</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>rovers</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>menorcitas</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>cuties</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>nutrias</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>panteritas</td>
                <td>4</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>flumifem</td>
                <td>3</td>
                <td>1</td>
                <td>1</td>
                <td>0</td>
                <td>0</td>
            </tr>
<tr>
                <td>ramoncitas</td>
                <td>3</td>
                <td>0</td>
                <td>0</td>
                <td>3</td>
                <td>0</td>
            </tr>
        </tbody>
    </table>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            actualizarTabla();
        });

        function actualizarTabla() {
            var tabla = document.getElementById('tablaPosiciones');
            var filas = tabla.querySelectorAll('tbody tr');

            filas.forEach(function(fila) {
                var partidosJugados = parseInt(fila.cells[1].textContent);
                var partidosGanados = parseInt(fila.cells[2].textContent);
                var partidosEmpatados = parseInt(fila.cells[3].textContent);

                var puntos = (partidosGanados * 3) + partidosEmpatados;
                fila.cells[5].textContent = puntos;
            });

            ordenarTabla();
        }

        function ordenarTabla() {
            var tabla = document.getElementById('tablaPosiciones');
            var tbody = tabla.querySelector('tbody');
            var filas = Array.from(tbody.querySelectorAll('tr'));

            // Ordenar filas por puntos (según la columna 5)
            filas.sort(function(a, b) {
                var puntosA = parseInt(a.cells[5].textContent);
                var puntosB = parseInt(b.cells[5].textContent);
                return puntosB - puntosA; // Orden descendente
            });

            // Limpiar tbody
            tbody.innerHTML = '';

            // Agregar filas ordenadas al tbody
            filas.forEach(function(fila) {
                tbody.appendChild(fila);
            });
        }
    </script>
</body>
</html>
