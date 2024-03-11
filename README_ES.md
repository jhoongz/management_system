# Sistema de Gestión de Proyectos

Este proyecto es un Sistema de Gestión de Proyectos creado con Django. Permite a los usuarios gestionar proyectos, asignar tareas, establecer plazos y hacer seguimiento del progreso de los proyectos.

## Características
- Creación, edición y eliminación de proyectos.
- Asignación de tareas a proyectos.
- Establecimiento de plazos para las tareas.
- Seguimiento del progreso de los proyectos y tareas.
- Interfaz de usuario intuitiva y fácil de usar.

## Tecnologías utilizadas
- Django
- HTML
- CSS
- JavaScript

## Instalación
1. Clona este repositorio: `git clone https://github.com/jhoongz/project_management_system.git`
2. Instala las dependencias: `pip install -r requirements.txt`
3. Realiza las migraciones de la base de datos: `python manage.py migrate`
4. Inicia el servidor: `python manage.py runserver`

## Uso
- Para acceder al sistema, abre tu navegador y visita `http://localhost:8000`
- Utiliza la interfaz para crear, editar y gestionar proyectos y tareas.

## Cargar Datos de Ejemplo
Para cargar los datos de ejemplo en la base de datos, sigue estos pasos:

1. Abre una terminal en el directorio raíz de tu proyecto.
2. Ejecuta el siguiente comando para iniciar la shell de Django:

   python manage.py shell

## Una vez en la shell de Django, copia y pega el siguiente código para cargar los datos de ejemplo:

from django.contrib.auth.models import User
from projects.models import Project, Task
from datetime import date

# Crear usuarios (si no existen ya en la base de datos)
manager1, _ = User.objects.get_or_create(username='manager1')
manager2, _ = User.objects.get_or_create(username='manager2')
manager3, _ = User.objects.get_or_create(username='manager3')

# Crear proyectos
project1 = Project.objects.create(
    name='Desarrollo de Aplicación Web',
    description='Creación de una aplicación web utilizando Django y React.',
    start_date=date(2023, 1, 15),
    end_date=date(2023, 6, 30),
    manager=manager1
)

project2 = Project.objects.create(
    name='Implementación de Sistema CRM',
    description='Implementación de un sistema CRM para gestionar clientes y ventas.',
    start_date=date(2023, 3, 10),
    end_date=date(2023, 9, 30),
    manager=manager2
)

project3 = Project.objects.create(
    name='Migración a la Nube',
    description='Migración de la infraestructura de servidores a la nube utilizando AWS.',
    start_date=date(2023, 5, 1),
    end_date=date(2023, 11, 30),
    manager=manager3
)

# Crear tareas (opcional)
task1 = Task.objects.create(
    project=project1,
    name='Diseño de la base de datos',
    description='Diseñar la estructura de la base de datos de la aplicación web.',
    assigned_to=manager1,
    due_date=date(2023, 2, 15),
    completed=False
)

task2 = Task.objects.create(
    project=project2,
    name='Configuración inicial del CRM',
    description='Configurar y personalizar el CRM según las necesidades de la empresa.',
    assigned_to=manager2,
    due_date=date(2023, 4, 10),
    completed=False
)

task3 = Task.objects.create(
    project=project3,
    name='Configuración de servidores en la nube',
    description='Configurar los servidores en la nube utilizando AWS.',
    assigned_to=manager3,
    due_date=date(2023, 6, 1),
    completed=False
)

## Contribución
Si quieres contribuir a este proyecto, por favor crea una rama (branch) nueva para tus cambios y envía un pull request con tus mejoras.

## Licencia
Este proyecto está bajo la Licencia MIT. Para más detalles, consulta el archivo LICENSE.
