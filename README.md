# ai-playground

Various AI fun stuff

|Title | Description |Colab |
|-|-|-|
|<b>[PerplexityAI clone](perplexity-clone/)</b>| A simple implementation to retrieve real-time data to feed to your large LLMs for QA tasks with references.| [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/mklarqvist/ai-playground/blob/main/perplexity-clone/perplexity_clone.ipynb)
🦙🧪 Laboratorio de llamas 🧬🦙
Llama Lab es un repositorio dedicado a la construcción de proyectos de vanguardia utilizando LlamaIndex.

LlamaIndex es una interfaz para el aumento de datos LLM. Proporciona herramientas fáciles de usar y flexibles para indexar varios tipos de datos. En esencia, se puede utilizar para indexar un corpus de conocimiento. Pero también se puede utilizar para indexar tareas y proporcionar capacidades similares a la memoria para cualquier abstracción de agente externo.

Aquí hay una descripción general de algunos de los increíbles proyectos que estamos explorando:

llama_agi (un proyecto inspirado en babyagi y AutoGPT para crear/planificar/y resolver tareas)
auto_llama (un proyecto inspirado en AutoGPT para buscar/descargar/consultar Internet para resolver tareas especificadas por el usuario).
Cada carpeta es un proyecto independiente. Vea a continuación una descripción de cada proyecto junto con ejemplos de uso.

Contribución: ¡Estamos muy abiertos a contribuciones! Esto puede incluir lo siguiente:

Ampliación de un proyecto existente
Crear un nuevo proyecto de Llama Lab
Modificar las capacidades en el repositorio principal de LlamaIndex para admitir proyectos de Llama Lab.
Laboratorios actuales
llama_agi
Inspirado en babyagi y AutoGPT, utilizando LlamaIndex como administrador de tareas y LangChain como ejecutor de tareas.

La versión actual de esta carpeta comenzará con un objetivo general ("resolver el hambre en el mundo" de forma predeterminada) y creará / priorizará las tareas necesarias para lograr ese objetivo. LlamaIndex se utiliza para crear y priorizar tareas, mientras que LangChain se utiliza para adivinar el "resultado" de completar cada acción.

Usando LangChain y LlamaIndex, llama_agi tiene acceso a las siguientes herramientas: búsqueda en Google, lectura de páginas web y toma de notas. Tenga en cuenta que la herramienta de búsqueda de Google requiere una clave API de Google y un ID de CSE.

Esto se ejecutará en un bucle hasta que la lista de tareas esté vacía (o tal vez se quede sin créditos de OpenAI) 😉).

Ejemplo de uso:

cd llama_agi
export OPENAI_API_KEY="key"
export GOOGLE_API_KEY="key"
export GOOGLE_CSE_ID="id"
python ./run_llama_agi.py --initial-task "Create a task list" --objective "Solve world hunger" --sleep 2
python ./run_llama_agi.py -h
usage: Llama AGI [-h] [-it INITIAL_TASK] [-o OBJECTIVE] [--sleep SLEEP]

A baby-agi/auto-gpt inspired application, powered by Llama Index!

options:
  -h, --help            show this help message and exit
  -it INITIAL_TASK, --initial-task INITIAL_TASK
                        The initial task for the system to carry out. Default='Create a list of tasks'
  -o OBJECTIVE, --objective OBJECTIVE
                        The overall objective for the system. Default='Solve World Hunger'
  --sleep SLEEP         Sleep time (in seconds) between each task loop. Default=2
auto_llama
Inspirado en autogpt. Esto implementa su propio sistema de agente similar a AutoGPT. Dada una consulta del usuario, este sistema tiene la capacidad de buscar en la web y descargar páginas web, antes de analizar los datos combinados y compilar una respuesta final a la solicitud del usuario.

Ejemplo de uso:

cd auto_llama
pip install -r requirements.txt
python -m auto_llama
Enter what you would like AutoLlama to do:
Summarize the financial news from the past week.
