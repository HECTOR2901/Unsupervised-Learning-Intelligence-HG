MusicDNA: Segmentación de Spotify y Sistema de Recomendación

**Descripción**

Este proyecto utiliza Machine Learning (Aprendizaje No Supervisado) para analizar un dataset de 114,000 canciones de Spotify. 
El objetivo es identificar patrones ocultos en las características de audio para agrupar canciones similares y construir un motor de recomendación basado en el "ADN musical" de cada pista.

**Pipeline del Proyecto**

- Carga y Limpieza: Procesamiento de datos masivos, manejo de errores de formato y normalización de tipos de datos.
- Análisis Exploratorio y Escalado: Uso de StandardScaler para que variables como el Tempo y la Energía tengan el mismo peso en el modelo.
- Método del Codo: Identificación matemática del número óptimo de grupos ($k=3$).Clustering con K-Means: Segmentación automática del catálogo en 3 grandes perfiles sonoros.
- Reducción de Dimensionalidad (PCA): Visualización en 2D de las 9 dimensiones de audio para validar la separación de los clústeres.
- Motor de Recomendación: Sistema funcional que sugiere 5 canciones similares basándose en la pertenencia al clúster.

**Interpretación de los Clústeres**

Tras el análisis de los centroides, los grupos se definieron así:

- **Cluster 0 (High Energy)**: Canciones intensas, con mucho volumen y ritmo rápido (Rock, Metal, EDM).
- **Cluster 1 (Acoustic/Chill)**: Música tranquila, con altos niveles de acústica y baja energía (Baladas, Clásica).
- **Cluster 2 (Dance/Pop)**: Canciones muy bailables, positivas y con presencia vocal (Pop, Reggaetón).

**Visualización de Resultados**
El análisis de Componentes Principales (PCA) demostró una separación clara entre los grupos:
<img width="734" height="541" alt="image" src="https://github.com/user-attachments/assets/a5642d1a-a5b2-47e0-acab-f7f9e8a39f55" />4

**Conclusión del Proyecto:**

El análisis demostró que las características matemáticas del audio (Music DNA) son suficientes para segmentar un catálogo masivo de forma coherente sin intervención humana.
Validación de Clústeres: Mediante el uso de PCA, se confirmó que el modelo K-Means ($k=3$) separa los datos en grupos con fronteras claras, lo que reduce el error de clasificación.
Eficiencia del Modelo: A pesar de la alta dimensionalidad inicial (9 variables), la normalización con StandardScaler permitió que el modelo fuera robusto frente a valores extremos en el Tempo o Loudness.
Escalabilidad: El sistema de recomendación desarrollado es escalable; puede procesar miles de nuevas entradas y asignarlas a un perfil sonoro instantáneamente, facilitando la creación de listas de reproducción automáticas personalizadas.

