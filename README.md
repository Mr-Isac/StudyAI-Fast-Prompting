# StudyAI - Fast Prompting

## Descripción

StudyAI es una prueba de concepto (POC) que utiliza inteligencia
artificial y técnicas de Prompt Engineering para generar planes de
estudio personalizados.

El proyecto busca ayudar a estudiantes a organizar sus materias,
temas y tiempo disponible mediante un plan de estudio generado por
un modelo de inteligencia artificial.

## Problema

Los estudiantes pueden tener dificultades para organizar diferentes
materias y contenidos dentro del tiempo disponible antes de una
evaluación.

StudyAI propone utilizar inteligencia artificial para transformar
estos datos en una planificación de estudio organizada.

## Objetivo

Desarrollar una POC que permita experimentar con diferentes técnicas
de prompting y evaluar cómo estas afectan la calidad y el control de
las respuestas generadas por un modelo de IA.

## Técnicas de Prompting

Durante el desarrollo se experimentaron:

- Prompting directo.
- Prompt estructurado.
- Few-shot prompting.
- Uso de restricciones.
- Prompts dinámicos.

Estas técnicas permitieron mejorar progresivamente la precisión y
control de las respuestas.

## Funcionamiento

El usuario proporciona:

- Materias y temas.
- Tiempo disponible por día.
- Cantidad de días disponibles.

Estos datos se incorporan dinámicamente a un prompt estructurado,
que luego es enviado al modelo de inteligencia artificial.

El flujo principal es:

Usuario → Datos → Prompt → Modelo de IA → Plan de estudio

## Tecnologías

- Python
- Jupyter Notebook
- Groq API
- Modelo `openai/gpt-oss-120b`
- python-dotenv

## Optimización

La implementación final utiliza una única consulta a la API para
generar cada plan de estudio, evitando consultas innecesarias y
reduciendo el consumo de recursos.

## Estructura

```text
StudyAI-Fast-Prompting/
│
├── StudyAI_Fast_Prompting.ipynb
├── README.md
├── .gitignore
└── .env
```

El archivo .env contiene las credenciales de la API y está excluido del repositorio mediante .gitignore.

El directorio .venv también está excluido porque contiene el entorno virtual local de Python y no es necesario subirlo a GitHub.

Instalación y ejecución

1. Instalar Python

El proyecto requiere Python instalado en el equipo.

2. Crear y activar el entorno virtual

Desde la carpeta del proyecto:

python -m venv .venv

Activar el entorno en Windows:

.venv\Scripts\activate

3. Instalar las dependencias
   pip install groq python-dotenv jupyter

4. Configurar la API Key

Crear un archivo .env en la raíz del proyecto:

GROQ_API_KEY=TU_API_KEY

Reemplazar TU_API_KEY por una API Key válida de Groq.

La API Key no debe compartirse ni subirse a GitHub.

5. Abrir Jupyter Notebook

Ejecutar:

python -m jupyter notebook

Luego abrir:

StudyAI_Fast_Prompting.ipynb

6. Ejecutar la POC

Ejecutar las celdas de la notebook en orden.

La POC solicitará al usuario:

Materias y temas.
Tiempo disponible por día.
Cantidad de días para estudiar.

Luego enviará los datos al modelo y mostrará el plan de estudio generado.

Resultados

La experimentación permitió observar que la incorporación de contexto, restricciones, ejemplos y una estructura clara mejora el control sobre las respuestas del modelo.

También se comprobó que el prompt puede reutilizarse con diferentes conjuntos de materias y temas.

Alcance

Esta entrega corresponde a una prueba de concepto desarrollada en Jupyter Notebook.

No se incluye una aplicación web completa. Una futura versión podría incorporar una interfaz web, generación de recursos visuales, seguimiento del progreso y mayor personalización.

Autor

Isaac Mendoza Rubio

Curso

Inteligencia artificial: Generación de Prompts

Comisión: 95920
