# UCU - Práctica 3: Webscraping

Webscraping - Proyecto para la Licenciatura en Datos y Negocios

## **Modalidad de presentación**

1. Debes crear un nuevo repositorio en tu cuenta de GitHub a partir de este Template. Para ello utiliza el botón "Utilizar este template"
2. Luego en tu repositorio, debes editar el archivo `project.ipynb` para resolver el proyecto.
3. Finalmente, presentar en WebAsignatura el enlace de tu repositorio.

## **Descripción del proyecto:**

Eres parte de un equipo de análisis de datos encargado de investigar y comparar los precios de compra de casas en distintas ciudades de Uruguay. Para ello, deberás **scrapear** una página web inmobiliaria que provea datos de propiedades en venta, como los precios, la ubicación y otros detalles relevantes.

Tu objetivo es realizar un **scraping** de los datos de las propiedades en venta en distintas ciudades de Uruguay y almacenarlos en un archivo **JSON** para su posterior análisis.

## **Requisitos del ejercicio:**

1. **Página web objetivo**: Utiliza una página web inmobiliaria de Uruguay que permita acceso público a sus listados de propiedades.

2. **Datos a extraer**:
   
   - **Ciudad**: Ciudad donde está ubicada la propiedad.
   - **Precio**: Precio de la propiedad en dólares (USD).
   - **Tamaño**: Tamaño de la propiedad en metros cuadrados (si está disponible).
   - **Número de habitaciones**: Cantidad de dormitorios (si está disponible).
   - **Link**: Enlace a la página del anuncio de la propiedad.

3. **Recolección de datos**:
   
   - Realiza scraping de las propiedades en al menos **tres ciudades diferentes** de Uruguay.
   - Extrae al menos **10 propiedades por ciudad**.

4. **Almacenamiento de datos**:
   
   - Los datos extraídos deben almacenarse en un archivo JSON con la siguiente estructura:
     
     ```json
     {
       "ciudades": [
         {
           "nombre": "Montevideo",
           "propiedades": [
             {
               "precio": 250000,
               "tamano": 150,
               "habitaciones": 3,
               "link": "https://www.ejemplo.com/propiedad1"
             },
             {
               "precio": 180000,
               "tamano": 120,
               "habitaciones": 2,
               "link": "https://www.ejemplo.com/propiedad2"
             }
           ]
         },
         {
           "nombre": "Punta del Este",
           "propiedades": [
             {
               "precio": 320000,
               "tamano": 180,
               "habitaciones": 4,
               "link": "https://www.ejemplo.com/propiedad3"
             }
           ]
         }
       ]
     }
     ```

5. **Requisitos técnicos**:
   
   - Utiliza la librería **`requests`** para hacer las solicitudes HTTP.
   - Utiliza la librería **`BeautifulSoup`** para analizar el HTML de la página.
   - Almacena los datos extraídos en un archivo **JSON** llamado `propiedades.json`.

6. **Formato de entrega**:
   
   - Entrega el código Python que realiza el scraping y la extracción de datos en el archivo `project.ipynb` de Jupiter Netbook.
   - Incluye el archivo `propiedades.json` con los resultados del scraping.

## **Pistas para la implementación**:

- Investiga en la web inmobiliaria seleccionada cómo están estructurados los datos de las propiedades (ej. etiqueta `<div>`, clases, etc.).
- Asegúrate de que el scraping respete los términos y condiciones de la página web que selecciones.
- Utiliza **`try-except`** para manejar posibles errores de conexión o de acceso a los elementos HTML.
- La estructura HTML puede variar según la página web, así que analiza cuidadosamente cómo están organizados los precios, la ubicación y los enlaces.

## **Criterios de evaluación**:

- Correcta implementación del scraping y extracción de los datos solicitados.
- Manejo eficiente de errores y control de excepciones.
- Formato correcto del archivo JSON generado.
- Calidad y claridad del código Python.
