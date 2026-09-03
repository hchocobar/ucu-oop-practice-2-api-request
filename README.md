# Práctica de API request

Este repositorio contiene el enunciado de la práctica de API request

## **Modalidad de presentación**

1. Debes crear un nuevo repositorio en tu cuenta de GitHub a partir de este Template. Para ello utiliza el botón "Utilizar este template"
2. Luego en tu repositorio, debes editar el archivo `project.ipynb` que se encuentra en el directorio `notebooks` para resolver el proyecto.
3. Finalmente, presentar en WebAsignatura el enlace de tu repositorio.

## **Criterios de evaluación**

- **PEP 8:** El código debe seguir las pautas de estilo de **PEP 8**.
- **Markdown:** El notebook `project.ipynb` debe estar bien documentado usando **Markdown** para explicar cada paso y los resultados obtenidos.
- **Funcionalidad:** Todas las tareas deben estar resueltas correctamente.
- **Requests:** Utilización correcta de la biblioteca `requests` para realizar la consulta HTTP.
- **JSON:** Correcta interpretación y manipulación de la respuesta JSON.
- **Python:** Uso adecuado de: listas, diccionarios, ciclos, funciones, comprensión de listas, cuando resulte apropiado

## Práctica: GitHub API — Análisis de repositorios

### **Introducción**

Eres parte de un equipo de análisis de datos encargado de estudiar la actividad y popularidad de proyectos de software desarrollados en GitHub.

Tu objetivo será **consumir la API REST de GitHub utilizando Python**, obtener información de los repositorios públicos de un usuario y transformar los datos obtenidos para realizar un pequeño análisis.

La API de GitHub permite consultar los repositorios públicos de un usuario mediante el endpoint:

```text
/users/{username}/repos
```

La consulta puede realizarse sin autenticación cuando se trabaja únicamente con recursos públicos.

---

#### Tarea 1 — Realizar una consulta a GitHub

Utiliza Python para consultar la API de GitHub y obtener los repositorios públicos de un usuario.

Puedes utilizar, por ejemplo:

```text
torvalds
```

o cualquier otro usuario de GitHub.

La respuesta de la API contiene información como:

* nombre del repositorio
* descripción
* lenguaje principal
* cantidad de estrellas
* cantidad de forks
* cantidad de issues
* fecha de creación
* fecha de última actualización
* URL del repositorio

---

#### Tarea 2 — Crear una lista de repositorios

A partir de la respuesta obtenida, crea una lista de diccionarios que contenga únicamente las siguientes claves:

```python
[{"name": "...",
  "language": "...",
  "stars": 123,
  "forks": 45},
 {"name": "...",
  "language": "...",
  "stars": 12,
  "forks": 5},
 {...}]
```

Los valores deberán obtenerse directamente de la respuesta de la API.

---

#### Tarea 3 — Analizar los repositorios

Utilizando la lista obtenida en la tarea anterior, responde mediante Python:

##### 3.1 Repositorio más popular

Determina cuál es el repositorio que tiene mayor cantidad de estrellas.

La salida esperada deberá tener un formato similar a:

```text
Most popular repository: xxx
Stars: 12345
```

##### 3.2 Lenguajes utilizados

Obtén los diferentes lenguajes de programación utilizados en los repositorios.

Por ejemplo:

```text
Languages:
- C
- C++
- Python
- JavaScript
```

##### 3.3 Cantidad de repositorios por lenguaje

Calcula cuántos repositorios utilizan cada lenguaje.

Resultado esperado:

```text
C: 5
Python: 3
JavaScript: 2
C++: 1
```

---

## Pistas para la implementación

### Paso 1 — Consultar la API

Puedes utilizar la biblioteca `requests`:

```python
import requests

url = "https://api.github.com/users/torvalds/repos"

response = requests.get(url)

response.raise_for_status()

data = response.json()
```

---

### Paso 2 — Explorar la respuesta

Antes de comenzar a procesar los datos, analiza la estructura de la respuesta.

Puedes consultar:

```python
type(data)
```

y:

```python
len(data)
```

También puedes inspeccionar uno de los elementos:

```python
data[0]
```

---

### Paso 3 — Crear la lista de diccionarios

Recorre los resultados y selecciona únicamente la información necesaria.

Por ejemplo:

```python
repositories = []

for repository in data:
    repositories.append({"name": repository["name"],
                         "language": repository["language"],
                         "stars": repository["stargazers_count"],
                         "forks": repository["forks_count"]})
```

**No es necesario utilizar exactamente este código.** El objetivo es que construyas tu propia solución.
