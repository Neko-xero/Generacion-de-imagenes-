Proyecto Final - Redes Neuronales y Aprendizaje Profundo
Descripción del Proyecto
Este proyecto implementa un sistema de Aprendizaje por Refuerzo (RL) para optimizar modelos de generación de imágenes basados en arquitecturas UnCLIP/Karlo. El objetivo principal es mejorar la calidad estética y la alineación semántica de las imágenes generadas mediante la optimización de parámetros LoRA (Low-Rank Adaptation) del modelo decoder, utilizando múltiples métricas de evaluación simultáneas.

Características Principales:
Entrenamiento RL con múltiples evaluadores: Combina métricas de estética visual, alineación CLIP, PickScore y HPSv2

Validación cruzada robusta: Implementa k-fold cross validation para evaluación justa del modelo

Búsqueda de hiperparámetros: Incluye búsqueda aleatoria automatizada para optimizar parámetros de LoRA y pesos de recompensa

Normalización inteligente: Normaliza todas las métricas a rangos comparables para evitar dominancia de escalas

Early stopping: Previene sobreajuste deteniendo el entrenamiento cuando no hay mejoras

Generación de imágenes de prueba: Produce muestras visuales para evaluación cualitativa
