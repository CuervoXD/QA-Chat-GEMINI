# ------- Pasos a seguir desde la terminal de VSCode -------


## 1. crear el entorno virtual (Terminal 1)
py -m venv .venv

## 3. Ingresar al entorno virtual
.\.venv\Scripts\activate

.\.venv\Scripts\Activate.ps1

## 2. Instalar dependencias:
python -m pip install --upgrade pip
pip install -r requirements.txt
pip install requests pandas colorama tabulate  [alternativo]
pip install openpyxl [alternativo]
pip list 


## 4. Ejecutar el programa
python app.py


### Relación e interacción entre los archivos del sistema

- Este proyecto funciona bajo una arquitectura cliente-servidor donde:

1.) Frontend (cliente): index.html + script.js

2.) Backend (servidor): app.py

- Modelo de IA: Gemini API

1. El flujo completo permite que el usuario escriba un mensaje, 
2. el servidor lo procese con el modelo de lenguaje y 
3. devuelva una respuesta.

### ------------------ Contexto de interacción ------------------

Usuario
   │
   ▼
index.html
   │
   ▼
script.js
   │
   │ fetch("/chat")
   ▼
Flask (app.py)
   │
   ▼
Gemini API
   │
   ▼
Flask responde JSON
   │
   ▼
script.js
   │
   ▼
Chat en pantalla


| Archivo    | Rol                                                          |
| ---------- | ------------------------------------------------------------ |
| index.html | Interfaz visual del chat                                     |
| script.js  | Maneja interacción del usuario y comunicación con el backend |
| app.py     | Servidor Flask que procesa mensajes                          |
| Gemini API | Modelo de IA que genera respuestas                           |


Usuario
   │
   ▼
Frontend (HTML + JS)
   │
   │ HTTP request
   ▼
Backend Flask
   │
   │ Prompt
   ▼
Gemini API
   │
   │ Respuesta
   ▼
Backend
   │
   ▼
Frontend
   │
   ▼
Usuario

### Pruebas - QA de Prompt Injection.

## Estructura
qa-tests/
│
├── payloads.json
├── metrics.py
├── test_prompt_injection.py
└── reports/

## Ejecutar pruebas QA (Terminal 2)

> Desde qa-tests:
cd qa-tests
python test_prompt_injection.py


## Revisar reportes

> Los reportes se generan en:
qa-tests/reports/

> Formatos generados:
JSON
Excel
HTML