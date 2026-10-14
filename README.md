# Sistema de Recomendación de Hoteles

Proyecto escolar en Python que usa una **red neuronal** para recomendar un hotel a partir de las preferencias del usuario: costo, ubicación y categoría (estrellas).

## ¿Qué hace?

El programa le pide al usuario tres datos:

| Preferencia | Valores |
|-------------|---------|
| Costo | 0 = bajo, 1 = medio, 2 = alto |
| Ubicación | 0 = lejos del centro, 1 = cerca |
| Estrellas | 1 a 5 |

Con esas respuestas, el modelo recomienda el hotel que mejor encaja con el perfil.

## Hoteles disponibles

| Hotel | Costo | Ubicación | Estrellas |
|-------|-------|-----------|-----------|
| Hotel Barato | Bajo | Lejos | 2 |
| Hotel Centro | Medio | Cerca | 3 |
| Hotel Lujo | Alto | Cerca | 5 |
| Hotel Playa | Medio | Lejos | 4 |
| Hotel Express | Bajo | Cerca | 1 |
| Hotel Familiar | Medio | Cerca | 4 |
| Hotel Rural | Bajo | Lejos | 3 |

## ¿Cómo funciona?

Se entrena una red neuronal de clasificación con 9 ejemplos creados a mano. Cada ejemplo asocia un perfil de preferencias con un hotel.

| Capa | Descripción |
|------|-------------|
| Entrada | 3 neuronas (costo, ubicación, estrellas) |
| Oculta 1 | 8 neuronas, activación ReLU |
| Oculta 2 | 5 neuronas, activación ReLU |
| Salida | 7 neuronas, activación softmax (una por hotel) |

- **Optimizador:** Adam
- **Función de pérdida:** sparse categorical crossentropy
- **Épocas:** 500

## Tecnologías

- Python
- TensorFlow / Keras
- NumPy
- Google Colab

## Cómo ejecutarlo

1. Abre el notebook en [Google Colab](https://colab.research.google.com/) (o usa el botón "Open in Colab" desde el archivo `.ipynb`).
2. Ejecuta todas las celdas en orden. Colab ya trae TensorFlow y NumPy instalados.
3. Responde las tres preguntas con los valores indicados.

Para correrlo en tu computadora:

```bash
pip install tensorflow numpy
```

## Ejemplo de uso

```
SISTEMA DE RECOMENDACIÓN DE HOTELES
Responde las siguientes preguntas:
Costo (0=bajo, 1=medio, 2=alto): 1
Ubicación (0=lejos del centro, 1=cerca): 1
Estrellas mínimas (1 a 5): 3

Hotel recomendado: Hotel Centro (índice 1)
```


## Limitaciones

- El conjunto de entrenamiento es muy pequeño (9 ejemplos), así que el modelo básicamente aprende a asociar perfiles con hoteles y no generaliza como un sistema real.
- Solo considera 7 hoteles y 3 características.
- No valida entradas fuera de rango (por ejemplo, un costo de 5).

## Autor

**Paola Vega** · Proyecto de la materia *Inteligencia Artificial*
