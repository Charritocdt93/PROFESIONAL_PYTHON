**Proyecto Final del Curso - Aplicación de Web Scraping en Python**

### Descripción del Proyecto:

El proyecto final consistirá en crear una aplicación de Web Scraping en Python que obtenga información sobre noticias o eventos desde un sitio web de noticias de https://www.telemadrid.es/. La aplicación deberá realizar las siguientes tareas:

1. **Obtención de Datos:**
   - Utilizar la librería `requests` para realizar una petición HTTP a un sitio web de noticias.
   - Utilizar `BeautifulSoup` para analizar el HTML y extraer información relevante, como títulos de noticias, fechas y enlaces.

2. **Almacenamiento de Datos:**
   - Guardar la información extraída en un archivo CSV para su posterior análisis.

3. **Visualización de Datos:**
   - Utilizar `matplotlib` para crear un gráfico o visualización que muestre la cantidad de noticias por fecha o por categoría.

4. **Interactividad:**
   - Permitir al usuario seleccionar la categoría de noticias que le interesa (por ejemplo, deportes, tecnología, política) y realizar el Web Scraping específicamente para esa categoría.

### Estructura del Proyecto:

```plaintext
proyecto_web_scraping/
│
├── src/
│   ├── web_scraping.py   # Código principal de Web Scraping
│   └── visualizacion.py  # Código para visualización de datos
│
├── data/
│   └── noticias.csv      # Archivo CSV para almacenar los datos
│
└── requirements.txt      # Archivo con las librerías necesarias
```

### Instrucciones para Ejecutar el Proyecto:

1. **Instalación de Librerías:**
   - Crear un entorno virtual (opcional, pero recomendado).
   - Ejecutar `pip install -r requirements.txt` para instalar las librerías necesarias.

2. **Ejecución del Código:**
   - Ejecutar el script `web_scraping.py` para realizar el Web Scraping y almacenar los datos en el archivo CSV.
   - Ejecutar el script `visualizacion.py` para crear y mostrar la visualización de datos.

### Notas Importantes:

- Asegúrate de revisar y cumplir con los términos de servicio del sitio web que estás consultando para evitar problemas legales.
- Es recomendable incluir manejo de errores y excepciones en tu código para lidiar con posibles problemas durante el Web Scraping.
- Considera la posibilidad de implementar la opción de seleccionar la categoría de noticias directamente desde la línea de comandos o mediante una interfaz gráfica simple.

Este proyecto te proporcionará una experiencia práctica en la aplicación de Web Scraping y te permitirá integrar los conocimientos adquiridos durante el curso, incluyendo el manejo de fechas, el uso de módulos, y posiblemente el trabajo con bases de datos para almacenar información a largo plazo.

USTED PODRA TOMAR EL CODIGO DE REFERENCIA Y:
DOCUMENTARLO 90% de la evaluación
CREAR UNA FUNCION 5% de la evaluación
COLOCARLO EN GITHUB 5% de la evaluación

codigo de referencia:
```
# importar el modulo request para extrar una pagina web
import requests
# importar del modulo bs4 la libreria BeautifulSoup para transformar el codigo en html
from bs4 import BeautifulSoup
from datetime import datetime


def webscraping(url_scraping,categoria_scraping='todas'):
    # URL de de telemadrid
    url = url_scraping

    # Realizar la petición
    try:
        respuesta = requests.get(url)
        #print(respuesta)
        #print(respuesta.text)
        # Verificar si la petición fue exitosa (código 200)
        if respuesta.status_code == 200:
            try:
                with open('../data/noticias.csv', 'w') as f:
                    f.write('titulo,url,categoria,fecha'+'\n')
                # Analizar el contenido con BeautifulSoup
            except:
                print("ERROR: no se pudo crear el archivo noticias.csv")
            try:
                soup = BeautifulSoup(respuesta.text, 'html.parser')
                #print(soup)
                # Aquí puedes realizar operaciones de Web Scraping
                # ...
                try:
                    noticias = soup.find_all('article', class_='card-news')
                    if noticias:
                        #print(noticias)
                        lista_categorias = []
                        for articulo in noticias:
                            #print(articulo)
                            try:
                                titulo = articulo.find('a', class_='oop-link').text.strip()
                                url_noticia = articulo.find('a', class_='opp-link')['href']
                                #print(url_noticia)
                                lista_url_noticia = url_noticia.split('/')
                                if lista_url_noticia[1] != '':
                                    categoria = lista_url_noticia[1]
                                else:
                                    categoria = lista_url_noticia[3]
                                lista_categorias.append(categoria)
                                lista_fecha = url_noticia.split('--')
                                fecha_caracteres = lista_fecha[1].replace('.html', '')
                                # print(fecha_caracteres)
                                # print(fecha_caracteres[0:4])
                                # print(fecha_caracteres[4:6])
                                # print(fecha_caracteres[6:8])
                                # print(fecha_caracteres[8:10])
                                # print(fecha_caracteres[10:12])
                                # print(fecha_caracteres[12:14])
                                fecha = datetime(int(fecha_caracteres[0:4]), int(fecha_caracteres[4:6]),
                                                 int(fecha_caracteres[6:8]))
                                fecha = fecha.strftime("%Y/%m/%d")
                                titulo = titulo.replace('\'','').replace('"','').replace(',','')
                                if categoria_scraping == 'todas':
                                    try:
                                        with open('../data/noticias.csv', 'a') as f:
                                            f.write(titulo+','+url_noticia+','+categoria+','+str(fecha)+'\n')
                                        # Analizar el contenido con BeautifulSoup
                                    except:
                                        print("ERROR: no se pudo anexar la noticia al archivo noticias.csv")
                                else:
                                    if categoria == categoria_scraping:
                                        try:
                                            with open('../data/noticias_'+categoria_scraping+'.csv', 'a') as f:
                                                f.write(titulo + ',' + url_noticia + ',' + categoria + ',' + str(
                                                    fecha) + '\n')
                                            # Analizar el contenido con BeautifulSoup
                                        except:
                                            print("ERROR: no se pudo anexar la noticia al archivo noticias.csv")
                            except:
                                try:
                                    titulo = articulo.find('a', class_='lnk').text.strip()
                                    url_noticia = articulo.find('a', class_='lnk')['href']
                                    lista_url_noticia = url_noticia.split('/')
                                    if lista_url_noticia[1] != '':
                                        categoria = lista_url_noticia[1]
                                    else:
                                        categoria = lista_url_noticia[3]
                                    lista_categorias.append(categoria)
                                    lista_fecha = url_noticia.split('--')
                                    fecha_caracteres = lista_fecha[1].replace('.html', '')
                                    #print(fecha_caracteres)
                                    #print(fecha_caracteres[0:4])
                                    #print(fecha_caracteres[4:6])
                                    #print(fecha_caracteres[6:8])
                                    #print(fecha_caracteres[8:10])
                                    #print(fecha_caracteres[10:12])
                                    #print(fecha_caracteres[12:14])
                                    fecha = datetime(int(fecha_caracteres[0:4]), int(fecha_caracteres[4:6]), int(fecha_caracteres[6:8]))
                                    fecha = fecha.strftime("%Y/%m/%d")
                                    titulo = titulo.replace('\'', '').replace('"', '').replace(',', '')
                                    if categoria_scraping == 'todas':
                                        try:
                                            with open('../data/noticias.csv', 'a') as f:
                                                f.write(titulo + ',' + url_noticia + ',' + categoria + ',' + str(
                                                    fecha) + '\n')
                                            # Analizar el contenido con BeautifulSoup
                                        except:
                                            print("ERROR: no se pudo anexar la noticia al archivo noticias.csv")
                                    else:
                                        if categoria == categoria_scraping:
                                            try:
                                                with open('../data/noticias_' + categoria_scraping + '.csv', 'a') as f:
                                                    f.write(titulo + ',' + url_noticia + ',' + categoria + ',' + str(
                                                        fecha) + '\n')
                                                # Analizar el contenido con BeautifulSoup
                                            except:
                                                print("ERROR: no se pudo anexar la noticia al archivo noticias.csv")
                                except:
                                    pass
                        #print(lista_categorias)
                        conjunto_categorias = set(lista_categorias)
                        #print(conjunto_categorias)
                    else:
                        print(f"Error La pagina {url} no contiene noticias")
                except:
                        print(f"ERROR: No se pudo encontrar articulos en el codigo html")
            except:
                print(f"ERROR: no se pudo convertir la pagina a codigo html")
        else:
            print(f"Error al obtener la página web. Código de estado: {respuesta.status_code}")
    except:
        print(f"ERROR: No se puede abrir la web pagina {url} o existe un error al procesarla")
    return conjunto_categorias


listado_categorias = webscraping('https://www.telemadrid.es/','todas')
seleccion = 'x'
while seleccion != '0':
    print("Lista de categorias: ")
    i = 1
    for opcion in listado_categorias:
        print(f"{i}.- {opcion}")
        i = i + 1
    print("0.- Salir")
    seleccion = input("Por favor seleccione una opcion indicando un numero:")
    categorias_listas = list(listado_categorias)
    categoria_seleccionada = categorias_listas[int(seleccion)-1]
    webscraping('https://www.telemadrid.es/', categoria_seleccionada)
```