# My First Agent 🤖

Este proyecto es un agente conversacional desarrollado con el **Agent Development Kit (ADK)** de Google, impulsado por el modelo de lenguaje **Gemini 3.5 Flash** (`gemini-3.5-flash`).

---

## 📁 Estructura del Proyecto

```text
my_first_agent/
├── agent.py           # Definición del agente principal (root_agent)
├── __init__.py        # Exporta el módulo del agente
├── requirements.txt   # Dependencias de Python necesarias
├── .env               # Variables de entorno y credenciales (API keys)
├── .gitignore         # Exclusiones de Git (.env, .adk/)
├── README.md          # Documentación y guía de uso
└── .adk/              # Almacenamiento local de sesiones (SQLite)
```

---

## 🚀 Inicio Rápido

Sigue esta secuencia de pasos para inicializar el proyecto y configurar el agente:

### 1. Crear entorno virtual
Crea y activa el entorno virtual de Python:

- **Windows (PowerShell):**
  ```powershell
  python -m venv .venv
  .\.venv\Scripts\Activate.ps1
  ```
- **Linux / macOS (Bash):**
  ```bash
  python3 -m venv .venv
  source .venv/bin/activate
  ```

### 2. Instalar ADK
Instala el paquete oficial de **Google Agent Development Kit (ADK)**:
```bash
pip install google-adk
```

### 3. Obtener clave de API
Genera tu clave de API de Gemini desde [Google AI Studio](https://aistudio.google.com/api-keys).

### 4. Configurar `.env`
Crea el archivo `.env` dentro de la carpeta `my_first_agent/` con tus credenciales:
```env
GOOGLE_API_KEY=tu_api_key_aqui
GOOGLE_GENAI_USE_ENTERPRISE=0
```

---

## 🧪 Cómo Probar y Ejecutar el Agente

El CLI de ADK ofrece tres modos principales para interactuar, depurar e integrar el agente:

### 1. Modo Consola (`adk run`)

Ideal para pruebas rápidas y depuración directa desde la terminal.

- **Modo interactivo (chat continuo):**
  ```bash
  adk run my_first_agent
  ```
  Permite conversar con el agente en tiempo real. Escribe tus preguntas y presiona `Enter`. Para salir, presiona `Ctrl + C` o escribe `exit`.

- **Consulta única (one-shot query):**
  ```bash
  adk run my_first_agent "¿Qué puedes hacer?"
  ```

---

### 2. Interfaz Gráfica Web (`adk web`)

Inicia un servidor local con una interfaz web visual donde puedes chatear, inspeccionar trazas, evaluar respuestas y ver el estado de las herramientas.

- **Iniciar la interfaz:**
  ```bash
  adk web my_first_agent
  ```
  *(O si estás dentro del directorio `my_first_agent`, puedes ejecutar `adk web .`)*

- **Acceder:**
  Abre tu navegador web en:
  👉 **[http://127.0.0.1:8000](http://127.0.0.1:8000)**

- **Opciones útiles:**
  - `--port <puerto>`: Cambia el puerto si el 8000 está ocupado (ej. `adk web my_first_agent --port 8080`).
  - `--reload`: Recarga automáticamente el servidor ante cambios en el código.

---

### 3. Servidor de API REST (`adk api_server`)

Inicia un servidor FastAPI sin la interfaz web visual, diseñado para integrar tu agente con aplicaciones externas, frontends personalizados o microservicios a través de endpoints REST.

- **Iniciar el servidor API:**
  ```bash
  adk api_server my_first_agent
  ```

- **Documentación interactiva (Swagger / OpenAPI):**
  Una vez iniciado el servidor, puedes explorar y probar todos los endpoints REST en:
  👉 **[http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)**
  👉 **[http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)**

- **Opciones útiles:**
  - `--auto_create_session`: Crea automáticamente una sesión si no existe al enviar consultas a `/run`.
  - `--port <puerto>`: Especifica un puerto diferente.
  - `--reload`: Habilita recarga automática durante el desarrollo.

---

