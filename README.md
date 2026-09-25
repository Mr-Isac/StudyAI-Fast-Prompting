# StudyAI - Fast Prompting

## Descripción

StudyAI es una prueba de concepto (POC) que utiliza inteligencia artificial y técnicas de Prompt Engineering para apoyar la planificación del estudio.

El proyecto busca ayudar a estudiantes a organizar sus materias, temas y tiempo disponible mediante un plan de estudio generado por un modelo de inteligencia artificial. Además, incorpora un modelo texto → imagen para complementar la planificación textual con una representación visual.

## Problema

Los estudiantes pueden tener dificultades para organizar diferentes materias y contenidos dentro del tiempo disponible antes de una evaluación.

StudyAI propone utilizar inteligencia artificial para transformar estos datos en una planificación de estudio organizada y complementarla con un recurso visual que facilite su comprensión.

## Objetivo

Desarrollar una POC que permita experimentar con diferentes técnicas de prompting y evaluar cómo estas afectan la calidad y el control de las respuestas generadas por modelos de inteligencia artificial.

La propuesta utiliza dos modalidades:

- Texto → texto: generación de planes de estudio.
- Texto → imagen: generación de una representación visual del plan.

## Técnicas de Prompting

Durante el desarrollo se experimentaron:

- Prompting directo.
- Prompt estructurado.
- Few-shot prompting.
- Uso de restricciones explícitas.
- Prompts dinámicos.
- Estructuración de prompts para generación de imágenes.

Estas técnicas permitieron mejorar progresivamente el control y la precisión de las respuestas y resultados generados por los modelos.

## Funcionamiento

El usuario proporciona:

- Materias y temas.
- Tiempo disponible por día.
- Cantidad de días disponibles.

Estos datos se incorporan dinámicamente a un prompt estructurado, que luego es enviado al modelo de inteligencia artificial.

El flujo principal del modelo texto → texto es:

Usuario → Datos → Prompt → Modelo de IA → Plan de estudio

Para el modelo texto → imagen se utiliza el concepto del plan generado como referencia para construir un prompt visual:

Plan de estudio → Prompt visual → Herramienta de generación de imágenes → Representación visual

La generación de imágenes se realizó mediante una herramienta externa gratuita, sin utilizar una API de imágenes.

## Tecnologías y herramientas

- Python
- Jupyter Notebook
- Groq API
- Modelo `openai/gpt-oss-120b`
- python-dotenv
- NightCafe
- GitHub

## Optimización

La implementación final del modelo texto → texto utiliza una única consulta a la API para generar cada plan de estudio, evitando consultas innecesarias y reduciendo el consumo de recursos.

En el modelo texto → imagen se experimentó con un prompt inicial y posteriormente con un prompt estructurado que incorpora:

- Rol.
- Objetivo.
- Contexto.
- Datos concretos.
- Elementos visuales.
- Restricciones.
- Estilo.
- Formato.

Esto permitió comparar el nivel de control obtenido mediante diferentes niveles de especificidad en las instrucciones.

## Estructura

```text
StudyAI-Fast-Prompting/
│
├── images/
│   ├── prompt_inicial.png
│   └── prompt_optimizado.png
│
├── StudyAI_Fast_Prompting.ipynb
├── README.md
└── .gitignore
```

El archivo `.env` se utiliza localmente para almacenar las credenciales de la API y está excluido del repositorio mediante `.gitignore`.

El directorio `.venv` también está excluido porque contiene el entorno virtual local de Python y no es necesario subirlo a GitHub.

## Instalación y ejecución

### 1. Instalar Python

El proyecto requiere Python instalado en el equipo.

### 2. Crear y activar el entorno virtual

Desde la carpeta del proyecto:

```text
python -m venv .venv
```

Activar el entorno en Windows:

```text
.venv\Scripts\activate
```

### 3. Instalar las dependencias

```text
pip install groq python-dotenv jupyter
```

### 4. Configurar la API Key

Crear un archivo `.env` en la raíz del proyecto:

```text
GROQ_API_KEY=TU_API_KEY
```

Reemplazar `TU_API_KEY` por una API Key válida de Groq.

La API Key no debe compartirse ni subirse a GitHub.

### 5. Abrir Jupyter Notebook

Ejecutar:

```text
python -m jupyter notebook
```

Luego abrir:

```text
StudyAI_Fast_Prompting.ipynb
```

### 6. Ejecutar la POC

Ejecutar las celdas de la notebook en orden.

La POC solicitará al usuario:

- Materias y temas.
- Tiempo disponible por día.
- Cantidad de días para estudiar.

Luego enviará los datos al modelo y mostrará el plan de estudio generado.

La sección texto → imagen contiene los prompts utilizados para generar las representaciones visuales y las imágenes obtenidas durante la experimentación.

## Resultados

La experimentación permitió observar que la incorporación de contexto, restricciones, ejemplos y una estructura clara mejora el control sobre las respuestas del modelo texto → texto.

También se comprobó que el prompt puede reutilizarse con diferentes conjuntos de materias y temas.

En el modelo texto → imagen, la comparación entre un prompt inicial y un prompt estructurado permitió observar que agregar contexto, datos específicos, restricciones, estilo y formato proporciona mayor control sobre las características esperadas de la imagen.

## Alcance

Esta entrega corresponde a una prueba de concepto desarrollada en Jupyter Notebook.

La solución combina dos modalidades de inteligencia artificial:

- Texto → texto para generar planes de estudio.
- Texto → imagen para generar recursos visuales relacionados con dichos planes.

No se incluye una aplicación web completa. Una futura versión podría incorporar una interfaz web, generación automática de recursos visuales a partir del plan generado, seguimiento del progreso y mayor personalización de los planes de estudio.

## Referencias

- Groq — Documentación oficial de la API.
- NightCafe — Plataforma de generación de imágenes mediante inteligencia artificial.
- OpenAI — Guías de Prompt Engineering.
- Python — Documentación oficial.
- Jupyter — Documentación oficial de Jupyter Notebook.

## Autor

Isaac Mendoza Rubio

## Curso

Inteligencia artificial: Generación de Prompts

## Comisión

95920
