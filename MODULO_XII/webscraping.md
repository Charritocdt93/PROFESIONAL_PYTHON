### ¿Qué es el Web Scraping?

El **Web Scraping** es una técnica de extracción de datos que consiste en obtener información desde páginas web. Utiliza código para navegar y extraer información estructurada desde el código fuente de una página web. Es útil para recopilar datos de interés, como precios, noticias, nombres, entre otros, de sitios web que no ofrecen interfaces de programación (API) para acceder a sus datos de manera directa.

### Librería BeautifulSoup:

**BeautifulSoup** es una librería en Python que facilita el Web Scraping al proporcionar métodos para extraer información de documentos HTML y XML de manera fácil y legible. Trabaja bien con bibliotecas como `requests` para obtener el contenido web y `lxml` o `html.parser` para analizar el HTML.

### Instalando las Librerías Necesarias:

Para instalar las librerías necesarias, puedes utilizar el siguiente comando en la terminal:

```bash
pip install beautifulsoup4 requests
```

### Realizando una Petición URL:

A continuación, se presenta un ejemplo básico de cómo realizar una petición a una URL y analizar el contenido con BeautifulSoup:

```python
import requests
from bs4 import BeautifulSoup

# URL de ejemplo
url = 'https://www.ejemplo.com'

# Realizar la petición
respuesta = requests.get(url)

# Verificar si la petición fue exitosa (código 200)
if respuesta.status_code == 200:
    # Analizar el contenido con BeautifulSoup
    soup = BeautifulSoup(respuesta.text, 'html.parser')
    
    # Aquí puedes realizar operaciones de Web Scraping
    # ...

else:
    print(f"Error al obtener la página. Código de estado: {respuesta.status_code}")
```

### Creando un Archivo CSV:

A menudo, es útil almacenar los datos extraídos en un formato estructurado, como CSV. Aquí hay un ejemplo de cómo crear un archivo CSV con la librería `csv` de Python:

```python
import csv

# Datos de ejemplo
datos = [
    {'Nombre': 'Ejemplo1', 'Edad': 25, 'Ciudad': 'Ciudad1'},
    {'Nombre': 'Ejemplo2', 'Edad': 30, 'Ciudad': 'Ciudad2'},
    # ...
]

# Escribir en un archivo CSV
with open('datos_extraidos.csv', 'w', newline='') as archivo_csv:
    campos = ['Nombre', 'Edad', 'Ciudad']
    escritor_csv = csv.DictWriter(archivo_csv, fieldnames=campos)
    
    # Escribir el encabezado
    escritor_csv.writeheader()
    
    # Escribir los datos
    escritor_csv.writerows(datos)
```

### Mostrando la Información en un Gráfico:

Para mostrar la información en un gráfico, puedes utilizar bibliotecas como `matplotlib` o `seaborn`. Aquí hay un ejemplo utilizando `matplotlib`:

```python
import matplotlib.pyplot as plt

# Datos de ejemplo
nombres = ['Ejemplo1', 'Ejemplo2']
edades = [25, 30]

# Crear un gráfico de barras
plt.bar(nombres, edades)
plt.xlabel('Nombres')
plt.ylabel('Edades')
plt.title('Edades de Ejemplos')

# Mostrar el gráfico
plt.show()
```

A continuación, una estructura generalizada del código con comentarios sobre dónde deberías adaptar la extracción de datos según el sitio web que elijas. Además, asegúrate de revisar y cumplir con los términos de servicio del sitio web para garantizar el uso ético y legal del Web Scraping.

```python
import requests
from bs4 import BeautifulSoup
import csv
import matplotlib.pyplot as plt

def obtener_datos_peliculas(url):
    # Realizar la petición a la URL
    respuesta = requests.get(url)

    # Verificar si la petición fue exitosa (código 200)
    if respuesta.status_code == 200:
        # Analizar el contenido con BeautifulSoup
        soup = BeautifulSoup(respuesta.text, 'html.parser')

        # Adaptar según la estructura del sitio web
        nombres = [nombre.text.strip() for nombre in soup.find_all('etiqueta_nombre', class_='clase_nombre')]
        clasificaciones = [float(clasificacion.text.strip()) for clasificacion in soup.find_all('etiqueta_clasificacion', class_='clase_clasificacion')]

        # Retornar los datos como un diccionario
        return {'Nombres': nombres, 'Clasificaciones': clasificaciones}
    else:
        print(f"Error al obtener la página. Código de estado: {respuesta.status_code}")
        return None

# Resto del código sigue siendo el mismo...
```

En este código, debes reemplazar 'etiqueta_nombre' y 'clase_nombre' con las etiquetas y clases HTML reales del sitio web que estás analizando. Haz lo mismo con 'etiqueta_clasificacion' y 'clase_clasificacion'. Utiliza las herramientas de desarrollador del navegador para inspeccionar el código fuente de la página y encontrar las etiquetas y clases correctas.

Recuerda siempre revisar y respetar los términos de servicio del sitio web, y ten en cuenta que algunos sitios web pueden tener medidas contra el Web Scraping.