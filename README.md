# Pluxis

**Vive experiencias que merecen ser recordadas.**

Pluxis es una aplicación web Full Stack para descubrir, explorar y reservar eventos. Permite consultar actividades, buscar eventos cercanos, gestionar reservas y acceder a funcionalidades personalizadas mediante autenticación de usuarios.

El proyecto está desarrollado con React y Vite en el frontend, Python y Flask en el backend y PostgreSQL como base de datos.

## Características principales

- Registro e inicio de sesión de usuarios.
- Autenticación mediante JSON Web Tokens (JWT).
- Protección de rutas privadas.
- Gestión y publicación de eventos.
- Organización de eventos por categorías.
- Consulta de información detallada de eventos.
- Búsqueda de eventos cercanos mediante geolocalización.
- Introducción manual de ubicaciones.
- Gestión de reservas.
- Subida y almacenamiento de imágenes mediante Cloudinary.
- Recuperación de contraseñas mediante correo electrónico.
- Interfaz responsive.
### Importante. Cuentas de  organizador  y usuario:
Organizador:  email: laura@eventify.com   password: 123456
Usuario: email: carlos@eventify.com password: 123456
Se pueden crear perfiles de usuarios desde el registro, pero no perfiles de organizadores ya que por seguridad lo gestionariamos nosotros

## Tecnologías utilizadas

### Frontend

- React 18
- JavaScript ES6+
- Vite 4
- React Router DOM 6
- HTML5
- CSS3
- Bootstrap 5
- Font Awesome 6
- Fetch API
- PropTypes

### Backend

- Python 3.13
- Flask
- Flask-SQLAlchemy
- SQLAlchemy
- Flask-Migrate
- Flask-JWT-Extended
- Flask-CORS
- Flask-Swagger
- Flask-Admin
- bcrypt
- Gunicorn

### Base de datos

- PostgreSQL
- Psycopg2

### Servicios externos

| Servicio | Funcionalidad |
| Cloudinary | Almacenamiento de imágenes |
| Geoapify | Geolocalización y búsqueda de ubicaciones |
| Gmail SMTP | Envío de correos de recuperación de contraseña |

### Herramientas

- Git
- GitHub
- GitHub Codespaces
- Postman
- Pipenv
- npm

## Arquitectura

Pluxis utiliza una arquitectura cliente-servidor.

- **Frontend:** interfaz desarrollada con React y Vite.
- **Backend:** API REST desarrollada con Flask.
- **Base de datos:** PostgreSQL gestionada mediante SQLAlchemy.
- **Autenticación:** JWT y contraseñas protegidas mediante bcrypt.
- **Servicios externos:** Cloudinary, Geoapify y SMTP.

## Estructura del proyecto

```text
Pluxis/
│
├── migrations/
│   └── versions/
│
├── public/
│
├── src/
│   ├── api/
│   │   ├── admin.py
│   │   ├── commands.py
│   │   ├── models.py
│   │   ├── routes.py
│   │   └── utils.py
│   │
│   ├── front/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── utils/
│   │   ├── index.css
│   │   ├── main.jsx
│   │   ├── routes.jsx
│   │   └── store.js
│   │
│   ├── app.py
│   └── wsgi.py
│
├── .env.example
├── .gitignore
├── package.json
├── Pipfile
├── Pipfile.lock
├── render.yaml
├── render_build.sh
└── README.md
```

## Instalación local

### Requisitos

- Python 3.13
- Node.js 20 o superior
- npm
- Pipenv
- PostgreSQL

### 1. Clonar el repositorio

```bash
git clone URL_DEL_REPOSITORIO
cd Pluxis
```

### 2. Instalar dependencias del frontend

```bash
npm install
```

### 3. Instalar dependencias del backend

```bash
pipenv install
```

### 4. Configurar las variables de entorno

Crear un archivo `.env` en la raíz del proyecto tomando como referencia `.env.example`.

Configurar las credenciales de PostgreSQL y los servicios externos.

### 5. Ejecutar el backend

```bash
pipenv run python src/app.py
```

### 6. Ejecutar el frontend

En otra terminal:

```bash
npm run dev
```

### 7. Compilar para producción

```bash
npm run build
```

Los archivos compilados se generan en la carpeta `dist/`.

## Variables de entorno

### Backend

```env
DATABASE_URL=
JWT_SECRET_KEY=

FLASK_DEBUG=0

CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=

GEOAPIFY_API_KEY=

FRONTEND_URL=

MAIL_SERVER=smtp.gmail.com
MAIL_PORT=587
MAIL_USERNAME=
MAIL_PASSWORD=
MAIL_DEFAULT_SENDER=
MAIL_USE_SSL=false
MAIL_USE_TLS=true
```

### Frontend

```env
VITE_BACKEND_URL=
```

`VITE_BACKEND_URL` debe contener la dirección base del backend, sin añadir `/api`.

**Seguridad:** nunca subir el archivo `.env` ni publicar credenciales, contraseñas o claves privadas en GitHub.

## Seguridad y autenticación

- Autenticación mediante JWT.
- Contraseñas protegidas mediante bcrypt.
- Rutas privadas y control de acceso.
- Gestión de sesiones y cierre de sesión cuando expira el token.
- Configuración CORS.
- Variables de entorno para credenciales y configuración.
- Recuperación de contraseña mediante enlaces temporales.

## Despliegue

El proyecto incluye archivos de configuración para preparar su despliegue en Render:

- `render.yaml`
- `render_build.sh`
- `Procfile`
- `Dockerfile.render`

El despliegue en producción está pendiente de completar y verificar.

## Autor: Aldo Alcivar Ferrin

Proyecto Full Stack desarrollado como aplicación web para descubrir y gestionar eventos.

**Vive experiencias que merecen ser recordadas.**
