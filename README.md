#Sistema RAG con Python en Google Colab

Este proyecto implementa un **sistema RAG (Retrieval-Augmented Generation)** utilizando **Python**, ejecutado en **Google Colab**, para construir un chatbot capaz de responder preguntas utilizando información recuperada de una base de documentos.

El sistema combina **búsqueda semántica** con **modelos de lenguaje**, permitiendo que el modelo genere respuestas basadas únicamente en el contexto recuperado.

---

#Tecnologías utilizadas

- Python
- LangChain
- FAISS (búsqueda vectorial)
- Sentence Transformers (generación de embeddings)
- Transformers (HuggingFace)
- TinyLlama 1.1B Chat
- ipywidgets (interfaz interactiva en Colab)
- PyTorch

---

#Funcionamiento del sistema

El flujo del sistema RAG se compone de varias etapas:

## Preparación de documentos
Se define un conjunto de documentos de ejemplo que contienen información sobre distintos temas tecnológicos.

## División de texto
Los documentos se dividen en fragmentos más pequeños utilizando un **Text Splitter** para mejorar la recuperación semántica.

## Generación de embeddings
Cada fragmento de texto se convierte en un **vector numérico (embedding)** utilizando un modelo de **Sentence Transformers**.

## Almacenamiento en base vectorial
Los embeddings se almacenan en una base vectorial utilizando **FAISS**, lo que permite realizar búsquedas semánticas rápidas.

## Recuperación de contexto (Retrieval)
Cuando el usuario realiza una pregunta, el sistema:

- Convierte la pregunta en embedding
- Busca los fragmentos más similares en la base vectorial
- Recupera los documentos más relevantes

## Generación de respuesta (Generation)
Los documentos recuperados se utilizan como **contexto** para un modelo de lenguaje (**TinyLlama**), que genera una respuesta basada únicamente en la información proporcionada.

## Interfaz interactiva
Se implementa una interfaz simple con **ipywidgets** que permite:

- Escribir una pregunta
- Ejecutar la búsqueda
- Mostrar el contexto recuperado
- Mostrar la respuesta generada

---

# Ejemplo de flujo

1. El usuario escribe una pregunta en la interfaz.
2. El sistema busca los documentos más relevantes.
3. Se construye un prompt con el contexto recuperado.
4. El modelo genera una respuesta basada en ese contexto.

---

# Instalación de dependencias

El notebook instala automáticamente las librerías necesarias:

```bash
pip install langchain
pip install langchain-community
pip install langchain-text-splitters
pip install sentence-transformers
pip install transformers
pip install accelerate
pip install faiss-cpu
pip install ipywidgets
