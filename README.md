# Sistema de Gestión de Estudiantes en Django

Este proyecto es un sistema educativo desarrollado en Django que permite gestionar estudiantes, incluyendo la creación, visualización y administración de sus datos básicos.

## Características del Proyecto

1. **Conexión con PostgreSQL**: Se utiliza PostgreSQL como base de datos.
2. **CRUD de Estudiantes**:
   - Listar estudiantes.
   - Crear nuevos estudiantes.
3. **Formulario Dinámico**: Uso de formularios basados en modelos para facilitar la entrada de datos.
4. **Interfaz de Administración**: Gestión de datos mediante el panel de administración de Django.
5. **Diseño Educativo**: Código claro y organizado para facilitar el aprendizaje de Django.

---

## Requisitos Previos

1. **Python**: Versiones 3.8 o superiores.
2. **Django**: Framework instalado (se explica más adelante).
3. **PostgreSQL**: Base de datos configurada en tu sistema.
4. **Virtualenv**: Herramienta para crear entornos virtuales.

---

## Instalación del Proyecto

### 1. Clonar el Repositorio
```bash
git clone <URL-DEL-REPOSITORIO>
cd proyecto_educativo
```

### 2. Crear y Activar un Entorno Virtual
```bash
# Crear entorno virtualirtualenv entorno_django

# Activar entorno virtual
# En Windows
.\entorno_django\Scripts\activate

# En Linux/Mac
source entorno_django/bin/activate
```

### 3. Instalar Dependencias
```bash
pip install django psycopg2
```

### 4. Configurar PostgreSQL

#### Crear la Base de Datos y Usuario en PostgreSQL
```sql
CREATE DATABASE bd_educativa;
CREATE USER usuario_bd WITH PASSWORD 'contrasena_segura';
GRANT ALL PRIVILEGES ON DATABASE bd_educativa TO usuario_bd;
```

#### Configurar `settings.py`
En el archivo `proyecto_educativo/settings.py`, configura la base de datos:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'bd_educativa',
        'USER': 'usuario_bd',
        'PASSWORD': 'contrasena_segura',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

### 5. Migrar la Base de Datos
```bash
python manage.py makemigrations\python manage.py migrate
```

### 6. Crear un Superusuario
```bash
python manage.py createsuperuser
```
Sigue las instrucciones en la terminal para configurar un superusuario.

### 7. Ejecutar el Servidor
```bash
python manage.py runserver
```

Accede al sistema en [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

---

## Estructura del Proyecto

```
proyecto_educativo/
    gestion_alumnos/
        templates/
            gestion_alumnos/
                index.html
                lista_estudiantes.html
                crear_estudiante.html
        migrations/
        __init__.py
        admin.py
        apps.py
        forms.py
        models.py
        tests.py
        urls.py
        views.py
    proyecto_educativo/
        __init__.py
        asgi.py
        settings.py
        urls.py
        wsgi.py
```

---

## Funcionalidades Principales

### 1. Página de Inicio
URL: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- Muestra un menú de navegación para acceder a las principales funcionalidades del sistema.

### 2. Listar Estudiantes
URL: [http://127.0.0.1:8000/estudiantes/](http://127.0.0.1:8000/estudiantes/)
- Muestra todos los estudiantes registrados en un formato de tabla.

### 3. Crear Estudiantes
URL: [http://127.0.0.1:8000/estudiantes/nuevo/](http://127.0.0.1:8000/estudiantes/nuevo/)
- Permite registrar nuevos estudiantes mediante un formulario dinámico basado en el modelo.

---

## Ampliaciones Futuras

1. **Edición y Eliminación de Estudiantes**:
   - Implementar vistas para editar y eliminar registros.
2. **Autenticación de Usuarios**:
   - Restringir ciertas páginas solo a usuarios autenticados.
3. **Paginación y Filtros**:
   - Implementar paginación y búsqueda en la lista de estudiantes.

---

## Recursos Educativos

- [Documentación Oficial de Django](https://docs.djangoproject.com/en/)
- [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- [Bootstrap para Diseños Responsivos](https://getbootstrap.com/)

---

## Licencia
Este proyecto es educativo y puede ser utilizado libremente para aprender o enseñar Django y PostgreSQL.
