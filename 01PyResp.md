---
title: "01Py - Resultado"
subtitle: "Fundamentos de Programación / Python"
author: "[Joanh](https://github.com/joanh)"
date: "2023"
output:
  html_document:
    theme: readable #sandstone #united
    highlight: tango
    keep_md: true
    toc: true
---





<style type="text/css">
pre, code {white-space:pre !important; overflow-x:auto}
</style>
------------------------------------------------------------------------

Soluciones al [ejercicio 01Py](https://github.com/SR1Agrupo/Python/blob/main/01Py.md)

------------------------------------------------------------------------

# `casi` Siempre hay más de una forma de hacer las cosas

## Eliminar elemento de la lista


```python
import random 

random_word_list = ['Oro', 'Diamantes', 'BitCoins', 'Incienso', 'Mirra', 'el Gordo'] 

# Se selecciona una palabra aleatoria de la lista
random_word_1 = random.choice(random_word_list) 
random_word_list.remove(random_word_1)           # y se elimina de la lista

print(f"Mi primer premio: ¡{random_word_1}!")
```

```
## Mi primer premio: ¡el Gordo!
```

```python
# Se selecciona otra palabra aleatoria de la lista actualizada
random_word_2 = random.choice(random_word_list)

print(f"y además... ¡{random_word_2}!")
```

```
## y además... ¡Incienso!
```

---

## Muestreo sin reemplazo


```python
import random 

random_word_list = ['Oro', 'Diamantes', 'BitCoins', 'Incienso', 'Mirra', 'el Gordo'] 

# Se selecciona una palabra aleatoria sin reemplazo
random_words = random.sample(random_word_list, 2)

print(f"Mis premios: ¡{random_words[0]}! y ¡{random_words[1]}!")
```

```
## Mis premios: ¡Incienso! y ¡Oro!
```

---

## Mezclar y asignar


```python
import random 

random_word_list = ['Oro', 'Diamantes', 'BitCoins', 'Incienso', 'Mirra', 'el Gordo'] 

# Se mezcla la lista y se seleccionan dos palabras
random.shuffle(random_word_list)
random_word_1 = random_word_list[0]
random_word_2 = random_word_list[1]

print(f"Mis premios: ¡{random_word_1}! + ¡{random_word_2}!")
```

```
## Mis premios: ¡Mirra! + ¡el Gordo!
```

---

## Verificar Duplicados


```python
import random 

def obtener_palabra_aleatoria_sin_duplicados(lista_palabras, lista_previamente_seleccionadas):
    palabras_disponibles = [palabra for palabra in lista_palabras if palabra not in lista_previamente_seleccionadas]

    if not palabras_disponibles:
        # Si ya se seleccionaron todas las palabras, reiniciar la lista previamente seleccionada
        lista_previamente_seleccionadas = []

    # Seleccionar una palabra aleatoria sin duplicados
    palabra_seleccionada = random.choice(palabras_disponibles)

    # Agregar la palabra seleccionada a la lista previamente seleccionada
    lista_previamente_seleccionadas.append(palabra_seleccionada)

    return palabra_seleccionada, lista_previamente_seleccionadas

# Lista de palabras
random_word_list = ['Oro', 'Diamantes', 'BitCoins', 'Incienso', 'Mirra', 'el Gordo'] 

# Lista para almacenar palabras previamente seleccionadas
palabras_previamente_seleccionadas = []

# Obtener una palabra aleatoria sin duplicados
random_word_1, palabras_previamente_seleccionadas = obtener_palabra_aleatoria_sin_duplicados(random_word_list, palabras_previamente_seleccionadas)

print(f"Mi primer premio: ¡{random_word_1}!")
```

```
## Mi primer premio: ¡Mirra!
```

```python
# Obtener otra palabra aleatoria sin duplicados
random_word_2, palabras_previamente_seleccionadas = obtener_palabra_aleatoria_sin_duplicados(random_word_list, palabras_previamente_seleccionadas)

print(f"y además... ¡{random_word_2}!")
```

```
## y además... ¡BitCoins!
```

---
