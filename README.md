# Prueba_InTechMOM

## API/GET
<p>Api/GET facilita la gestión de obtener objetos específicos de un listado de una lista de usuarios en formato JSON a través de la API https://randomuser.me/documentation. Se emplea el método GET en el endpoint users para llevar a cabo esta actividad. Esta API devuelve un conjunto predeterminado de 10 usuarios en formato JSON, aunque este valor puede ajustarse con el parámetro opcional (/users?limit=5). Además, ofrece la posibilidad de filtrar y reorganizar el JSON según el género de los usuarios (categorize=gender). Es importante destacar que la API oculta información sensible y garantiza que no se repitan los usuarios..</p>

### TECNOLOGÍAS

[![Github](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)]() [![Python Version](https://img.shields.io/badge/python-3.6%2B-blue)]() ![Django Version](https://img.shields.io/badge/django-3.2-green)


### INSTALACIÓN – CONFIGURACIÓN

<p> Para llevar a cabo el proyecto en un repositorio local mediante la terminal con PowerShell, sigue las indicaciones que se detallan a continuación:</p>

- Crear un repositorio en GitHub
- Clonar el repositorio en VSC dentro de la carpeta que hayas seleccionado
```code
git clone https://github.com/ginadevelop/Prueba_InTechMOM.git
```
- Crear otra rama para realizar pruebas, llamada en este caso, develop
```code
git branch develop
```
- Utiliza la página web https://www.toptal.com/developers/gitignore para generar un archivo .gitignore personalizado. Selecciona los lenguajes de programación que planeas utilizar, en este caso, PYTHON y DJANGO. Crea un archivo .gitignore en tu repositorio local y copia el contenido generado por la página web. Este archivo ayudará a excluir archivos y directorios específicos relacionados con los lenguajes seleccionados al realizar operaciones con Git.
- Crea un archivo llamado ".env" en tu proyecto para gestionar las variables de entorno relacionadas con la base de datos
```code
pyhton -m ven env
```
- Activar el entorno virtual
```code
.\env\Scripts\Activate.ps1
```
- Instalar los paquetes necesarios 
```code
pip install django
pip install django restframework
pip install request
pip install pytz
```
- Verificar que todos los paquetes se hayan copiado directamente 
```code
pip list
```
- Copia los resultados de pip list y guárdalos en un archivo llamado "requirements.txt" para documentar las dependencias de tu proyecto.

```code
asgiref==3.7.2
certifi==2023.11.17
charset-normalizer==3.3.2
Django==4.2
django-cors-headers==3.14.0
djangorestframework==3.14.0
idna==3.6
pip==23.3.2
pytz==2023.3
requests==2.31.0
sqlparse==0.4.4
tzdata==2023.3
urllib3==2.1.0
```
- Cuando necesites continuar con el proyecto desde otro computador. Clone el repositorio e Instale todas las dependencias necesarias ejecutando el siguiente comando:
```code
pip install -r requirements.txt
```
- Instalar un proyecto llamado “api”
```code
django-admin startproject api
```
- Instalar una app llamada “users”
```code
python manage.py startapp users
```
- Configurar el archivo api.settings.py, adicionando la app “users”
```code
INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'users',
]
```
- Desarrollar el código para implementar funciones específicas de la API en el archivo users.views.py. Es necesario revisar los detalles mencionados en el archivo views, los cuales están especificados en el repositorio.
- Crear un archivo llamado “urls.py” en la app “users” y configurarlo
```code
from django.urls import path
from .views import UsersView
urlpatterns = [
    path('', UsersView.as_view(), name='users'),    
]
```
- Configurar el archivo api.urls.py, adicionando la urls de la app “users”
```code
from django.urls import path, include
urlpatterns = [
    path('admin/', admin.site.urls),
    path('users/', include("users.urls")),
]
```
- Crear archivos de migración de bases de datos en función de los cambios realizados
```code
python manage.py makemigrations
```
- Ejecutar las migraciones para aplicar los cambios a la base de datos
```code
python manage.py migrate
```
- Verificar si la página web está en ejecución.
```code
python manage.py runserver
```
- Finalmente realizar pull request con la rama “main”. 

### RUTAS API

- Al acceder a http://127.0.0.1:8000/users/, se visualizan por defecto 10

[![10_usuarios](https://github.com/ginadevelop/Prueba_InTechMOM/blob/develop/images/Captura1.JPG)]

- Al acceder a http://127.0.0.1:8000/users/?limit=1, se restringe la respuesta JSON a un único usuario

[![1_usuario](https://github.com/ginadevelop/Prueba_InTechMOM/blob/develop/images/Captura2.JPG)]

- Mediante http://127.0.0.1:8000/users/?categorize=gender se aplica un filtro para organizar el JSON por género.

[![genero](https://github.com/ginadevelop/Prueba_InTechMOM/blob/develop/images/Captura3.JPG)]



