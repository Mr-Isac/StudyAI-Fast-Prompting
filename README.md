# StudyAI - Fast Prompting

## Descripción

StudyAI es una prueba de concepto (POC) que utiliza inteligencia artificial y técnicas de Prompt Engineering para generar planes de estudio personalizados.

El proyecto busca ayudar a estudiantes a organizar sus materias, temas y tiempo disponible mediante un plan de estudio generado por un modelo de inteligencia artificial.

Además, el proyecto incorpora un componente de generación de imágenes mediante texto → imagen para representar visualmente el plan de estudio.

## Problema

Los estudiantes pueden tener dificultades para organizar diferentes materias y contenidos dentro del tiempo disponible antes de una evaluación.

StudyAI propone utilizar inteligencia artificial para transformar estos datos en una planificación de estudio organizada y complementarla con una representación visual que facilite su comprensión.

## Objetivo

Desarrollar una POC que permita experimentar con diferentes técnicas de Prompt Engineering y evaluar cómo estas afectan la calidad y el control de las respuestas generadas por modelos de IA.

El proyecto utiliza dos modalidades:

- Texto → texto: generación de planes de estudio.
- Texto → imagen: generación de una representación visual del plan de estudio.

## Técnicas de Prompting

Durante el desarrollo se experimentaron diferentes técnicas:

- Prompting directo.
- Prompt estructurado.
- Few-shot prompting.
- Uso de restricciones.
- Prompts dinámicos.
- Estructuración de prompts para generación de imágenes.

Estas técnicas permitieron mejorar progresivamente la precisión, el control y la especificidad de las respuestas generadas.

## Funcionamiento

### Texto → texto

```text
Usuario → Datos → Prompt → Modelo de IA → Plan de estudio
```

El usuario proporciona información como materias, temas, fecha del examen y tiempo disponible. Estos datos son incorporados al prompt y enviados al modelo de IA para generar una planificación personalizada.

### Texto → imagen

```text
Plan de estudio → Prompt visual → NightCafe → Representación visual
```

El plan de estudio sirve como referencia para construir un prompt orientado a generar una representación visual organizada por días, materias, temas y sesiones de estudio.

## Tecnologías y herramientas

- Python
- Jupyter Notebook
- Groq API
- Modelo `openai/gpt-oss-120b`
- python-dotenv
- NightCafe
- GitHub

### Generación de imágenes

Para el componente texto → imagen se utilizó NightCafe como herramienta gratuita de generación visual.

Se seleccionó una composición horizontal debido a que el resultado representa un plan de estudio organizado por días y materias, permitiendo distribuir visualmente la información de manera clara.

Las imágenes generadas fueron incorporadas al repositorio como evidencia de la experimentación.

## Optimización

La implementación del modelo texto → texto utiliza una única consulta a la API para generar cada plan de estudio, evitando consultas innecesarias y reduciendo el consumo de recursos.

Para el modelo texto → imagen se experimentó inicialmente con un prompt general y posteriormente con un prompt estructurado que incorpora:

- Rol.
- Objetivo.
- Contexto.
- Datos concretos.
- Elementos requeridos.
- Restricciones.
- Estilo visual.
- Formato.

La comparación permitió observar cómo una mayor especificidad en las instrucciones proporciona mayor control sobre las características esperadas de la imagen.

## Estructura del proyecto

```text
StudyAI-Fast-Prompting/
├── images/
│   ├── prompt_inicial.webp
│   └── prompt_optimizado.webp
├── StudyAI_Fast_Prompting.ipynb
├── README.md
└── .gitignore
```

Los archivos `.env` y `.venv` se mantienen fuera del repositorio mediante `.gitignore`.

## Instalación y ejecución

### 1. Clonar el repositorio

```bash
git clone https://github.com/Mr-Isac/StudyAI-Fast-Prompting.git
```

### 2. Crear y activar el entorno virtual

```bash
python -m venv .venv
```

En Windows:

```bash
.venv\Scripts\activate
```

### 3. Instalar las dependencias

```bash
pip install groq python-dotenv jupyter
```

### 4. Configurar la API Key

Crear un archivo `.env` en la raíz del proyecto:

```text
GROQ_API_KEY=tu_api_key
```

La API Key no debe incluirse directamente en el código ni subirse al repositorio.

### 5. Ejecutar Jupyter Notebook

```bash
python -m jupyter notebook
```

Abrir el archivo:

```text
StudyAI_Fast_Prompting.ipynb
```

y ejecutar las celdas en orden.

## Resultados

La experimentación permitió comprobar que las técnicas de Fast Prompting mejoran el control sobre las respuestas generadas por el modelo de texto → texto.

La utilización de prompts estructurados y restricciones permitió obtener planes de estudio más organizados y adaptados a los datos proporcionados por el estudiante.

En el modelo texto → imagen, el prompt inicial permitió obtener una representación general de un plan de estudio, mientras que el prompt optimizado incorporó información específica, restricciones y características visuales para orientar mejor la generación.

La comparación de ambos resultados permitió observar que las técnicas de estructuración y especificidad también pueden aplicarse a modelos texto → imagen.

## Alcance

El proyecto corresponde a una prueba de concepto desarrollada en Jupyter Notebook.

Como trabajo futuro, StudyAI podría evolucionar hacia una aplicación web completa que incorpore:

- Generación automática de recursos visuales.
- Seguimiento del progreso del estudiante.
- Personalización avanzada de los planes de estudio.
- Integración de diferentes modelos de inteligencia artificial.

## Referencias

- Groq. (2026). Groq API Documentation.
  https://console.groq.com/docs

- NightCafe. (2026). AI Art Generator.
  https://creator.nightcafe.studio/

- OpenAI. (2026). Prompt engineering guide.
  https://platform.openai.com/docs/guides/prompt-engineering

- Python Software Foundation. (2026). Python Documentation.
  https://docs.python.org/3/

- Project Jupyter. (2026). Jupyter Notebook Documentation.
  https://docs.jupyter.org/en/latest/

## Autor

**Isaac Mendoza Rubio**

### Curso

Inteligencia Artificial: Generación de Prompts

### Comisión

95920
