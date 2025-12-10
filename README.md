# Proyecto Final - IA: Entrenamiento RL para Modelos de Generación de Imágenes

## Descripción del Proyecto

Este proyecto implementa un sistema de **Aprendizaje por Refuerzo (RL)** para optimizar modelos de generación de imágenes basados en arquitecturas **UnCLIP/Karlo**. El objetivo principal es mejorar la calidad estética y la alineación semántica de las imágenes generadas mediante la optimización de parámetros LoRA (Low-Rank Adaptation) del modelo decoder, utilizando múltiples métricas de evaluación simultáneas.

### Características Principales:

- **Entrenamiento RL con múltiples evaluadores**: Combina métricas de estética visual, alineación CLIP, PickScore y HPSv2
- **Validación cruzada robusta**: Implementa k-fold cross validation para evaluación justa del modelo
- **Normalización inteligente**: Normaliza todas las métricas a rangos comparables para evitar dominancia de escalas
- **Early stopping**: Previene sobreajuste deteniendo el entrenamiento cuando no hay mejoras
- **Generación de imágenes de prueba**: Produce muestras visuales para evaluación cualitativa

### Archivos Principales:

#### 1. **entrenamiento.ipynb** - Notebook Principal de Entrenamiento
Este archivo contiene la implementación completa del sistema de entrenamiento RL con las siguientes funcionalidades:

- **Carga y configuración del modelo UnCLIP/Karlo**: Inicializa la pipeline de generación de imágenes
- **Implementación de LoRA (Low-Rank Adaptation)**: Aplica adaptación de bajo rango al decoder del modelo
- **Sistema de evaluación multi-métrica**: Integra 4 evaluadores simultáneos:
  - Estética visual (basada en CLIP)
  - Alineación texto-imagen (CLIP alignment)
  - PickScore (modelo de preferencia humana)
  - HPSv2 (Human Preference Score v2)
- **Validación cruzada (k-fold)**: Divide los datos en múltiples folds para evaluación robusta
- **Búsqueda aleatoria de hiperparámetros**: Automatiza la optimización de parámetros
- **Early stopping automático**: Detiene el entrenamiento cuando no hay mejoras
- **Generación y guardado de imágenes**: Produce muestras visuales de los resultados

#### 2. **environment.yml** - Configuración del Ambiente Conda
Archivo de configuración que define todas las dependencias necesarias para el proyecto:

- **Ambiente específico**: `rl-unclip-env`
- **Versiones controladas**: Especifica versiones exactas para reproducibilidad
- **Dependencias clave**:
  - PyTorch 2.0.1 con soporte CUDA 11.7
  - Diffusers y Transformers (Hugging Face)
  - PEFT (Parameter-Efficient Fine-Tuning) para LoRA
  - OpenCLIP para modelos CLIP
  - Jupyter Notebook para ejecución interactiva



## Requisitos y Configuración del Ambiente

### 1. Configuración Inicial

**Requisitos de Sistema:**
- Python 3.8+
- CUDA 11.7+ (recomendado para aceleración GPU)
- 16GB+ RAM
- 20GB+ espacio en disco para modelos

### 2. Configuración del Ambiente Conda

El archivo `environment.yml` contiene todas las dependencias necesarias. Para crear el ambiente:
## Fuente de Datos

Los prompts utilizados para entrenamiento y validación fueron obtenidos del dataset **DiffusionDB**, un conjunto de datos a gran escala de prompts e imágenes generadas por modelos de difusión. El dataset está disponible públicamente en Hugging Face:

- **Dataset**: DiffusionDB
- **URL**: https://huggingface.co/datasets/poloclub/diffusiondb/tree/main
- **Contenido**: Millones de prompts utilizados para generar imágenes con modelos Stable Diffusion
- **Licencia**: Creative Commons CC0 1.0

