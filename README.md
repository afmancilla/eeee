# Juego Quarto con Agente Inteligente

Implementación del juego Quarto con un agente inteligente basado en búsqueda adversarial usando minimax con poda alfa-beta.

## Características

- Interfaz gráfica con Tkinter
- Interfaz de línea de comandos
- Agente inteligente proactivo basado en objetivos
- Búsqueda adversarial con minimax y poda alfa-beta
- Frecuencia de muestreo configurable
- Estadísticas de rendimiento del agente integradas
- Capturas automáticas del juego

## Requisitos

- Python 3.8 o superior
- Paquetes requeridos:
  - pillow (para capturas)
  - pytest (para pruebas)
  - black (para formateo)
  - pylint (para análisis de código)

## Instalación

1. Clonar el repositorio:
```bash
git clone <url-repositorio>
cd quarto
```

2. (Opcional) Crear un entorno virtual:
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

3. Instalar dependencias:
```bash
pip install -r requirements.txt
```

## Uso

### Ejecución por defecto
```bash
python main.py
```
Esto iniciará el juego en modo gráfico con Tkinter, con el humano como primer jugador y frecuencia de 1.0 Hz para el agente.

### Interfaz de Línea de Comandos
```bash
python main.py --modo cli
```

### Opciones adicionales
- `--modo`: Selecciona el modo de interfaz (tk/cli)
- `--frecuencia`: Frecuencia de muestreo del agente en Hz (por defecto: 1.0)
- `--primer_jugador`: Jugador que inicia la partida (humano/agente)

Ejemplos:
```bash
python main.py --modo tk --primer_jugador agente
python main.py --modo tk --frecuencia 0.5
```

## Reglas del Juego

### Tablero y Piezas
- Tablero de 4x4 casillas
- 16 piezas únicas con 4 atributos binarios:
  - Tamaño: Grande/Pequeña
  - Color: Roja/Azul
  - Forma: Redonda/Cuadrada
  - Solidez: Sólida/Hueca

### Mecánica de Juego
1. Los jugadores alternan turnos
2. Cada turno tiene dos fases:
   - COLOCAR: El jugador coloca la pieza activa en el tablero
   - SELECCIONAR: El jugador selecciona una pieza para el oponente

### Victoria
- Completar una línea de 4 piezas (horizontal, vertical o diagonal) que compartan al menos un atributo
- Si el tablero se llena sin líneas ganadoras, el juego termina en empate

## Interfaz Gráfica

### Disposición
- Panel izquierdo: Tablero de juego 4x4
- Panel central: Piezas disponibles y registro de jugadas
- Panel derecho: Estado del juego y estadísticas

### Controles
- Click izquierdo para:
  - Seleccionar pieza (fase SELECCIONAR)
  - Colocar pieza en tablero (fase COLOCAR)
- Botón Reiniciar: Comienza nueva partida
- Botón Salir: Cierra el juego

### Características
- Resaltado visual de piezas y casillas
- Indicadores claros de fase actual y turno
- Estadísticas en tiempo real del agente
- Captura automática de jugadas (opcional)
- Guardado de logs y estadísticas

## Interfaz de Línea de Comandos

### Comandos
- `mostrar`: Muestra el estado actual del juego
- `seleccionar N`: Selecciona la pieza número N
- `colocar F C`: Coloca la pieza activa en la fila F, columna C
- `ayuda`: Muestra las instrucciones
- `salir`: Termina el juego

## Agente Inteligente

### Características
- Tipo: Agente proactivo basado en objetivos
- Estrategia: Búsqueda adversarial con minimax
- Optimización: Poda alfa-beta
- Percepción: Muestreo configurable del estado del juego

### Heurísticas
- Evaluación de líneas potenciales
- Análisis de atributos compartidos
- Bloqueo de victorias del oponente
- Maximización de oportunidades propias

## Desarrollo

### Estructura del Proyecto
```
quarto/
├── src/
│   ├── juego/
│   │   ├── pieza.py
│   │   ├── tablero.py
│   │   └── estado.py
│   ├── agente/
│   │   └── agente.py
│   └── interfaces/
│       ├── tk_gui.py
│       └── cli.py
├── tests/
├── main.py
├── requirements.txt
└── README.md
```

### Contribuir
1. Crear un fork del repositorio
2. Crear una rama para tu característica
3. Hacer commit de tus cambios
4. Crear un pull request
