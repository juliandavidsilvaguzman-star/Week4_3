# Week4_3 – Optimización en una Red Neuronal
# Descripción general
Este proyecto tiene como objetivo analizar el impacto de diferentes optimizadores en el entrenamiento de una red neuronal, manteniendo constante la arquitectura del modelo, el conjunto de datos y los hiperparámetros principales.
La comparación se realiza utilizando los optimizadores Stochastic Gradient Descent (SGD) y Adam, aplicados al conjunto de datos MNIST para clasificación de dígitos manuscritos.

# Dataset

MNIST: conjunto de imágenes en escala de grises de dígitos del 0 al 9.
Cada imagen se transforma en un vector de 784 características (28×28).
Los valores de los píxeles se normalizan entre 0 y 1.
Las etiquetas se convierten a one-hot encoding para clasificación multiclase.


# Arquitectura del modelo
Se define una arquitectura base que se utiliza sin modificaciones en todos los experimentos, garantizando una comparación justa entre optimizadores:

Capa densa oculta con 64 neuronas y activación ReLU
Capa densa oculta con 32 neuronas y activación ReLU
Capa de salida con 10 neuronas y activación Softmax

La función de pérdida utilizada es categorical_crossentropy, adecuada para clasificación multiclase.

# Proceso de entrenamiento
El modelo se entrena bajo las mismas condiciones para ambos optimizadores:

Épocas: 15
Batch size: 128
Validation split: 20%
Métrica de evaluación: Accuracy

# Optimización con SGD

Optimizador: SGD
Tasa de aprendizaje: 0.01
Presenta una convergencia progresiva y estable, pero más lenta.
Requiere un mayor número de épocas para alcanzar buen desempeño.

# Optimización con Adam

Optimizador: Adam
Tasa de aprendizaje: 0.001
Combina momentum y tasas de aprendizaje adaptativas.
Logra una convergencia mucho más rápida y una reducción significativa del loss en pocas épocas.


# Evaluación del modelo
Los modelos se evalúan sobre el conjunto de prueba (test):


# Optimizador   	    Loss    	Accuracy
    SGD	            ≈ 0.22	   ≈ 93.6%
    Adam          	≈ 0.10	   ≈ 97.3%
Además, se grafica la evolución del loss por época, donde Adam muestra una caída más rápida y estable en comparación con SGD.

# Conclusiones

- Adam presenta una convergencia más rápida y estable que SGD en el entrenamiento de redes neuronales.
- SGD es altamente sensible a la tasa de aprendizaje, lo que puede ralentizar el proceso si no se ajusta correctamente.
- El optimizador influye directamente en:
             La velocidad de aprendizaje
             La estabilidad del entrenamiento
             El desempeño final del modelo


- Para problemas de clasificación como MNIST, Adam resulta más eficiente cuando no se realiza un ajuste fino de hiperparámetros.
- Mantener constante la arquitectura permitió aislar el efecto del optimizador, facilitando una comparación objetiva.****
