# Gestión Automatizada de Biblioteca 📚

Este proyecto facilita la gestión de usuarios y libros mediante flujos de trabajo automatizados con GitHub Actions. A continuación, se describen las funcionalidades principales.

---

## **1. Registrar Usuario**
Permite registrar nuevos usuarios y genera automáticamente directorios y archivos personalizados.

### Flujo de trabajo
- **Archivo**: `register-user.yml`

### Características
- Solicita datos como nombre, apellidos, correo electrónico y preferencia de notificaciones.
- Crea un ID único para el usuario.
- Actualiza un archivo global de usuarios (`users.json`) y genera un README personal.

### Archivos generados
- `Usuarios/[nombre]_[id]/README.md`
- `Usuarios/users.json`

---

## **2. Registrar Libro**
Añade libros a la biblioteca personal de un usuario registrado y clasifica los libros por estado.

### Flujo de trabajo
- **Archivo**: `add-book.yml`

### Características
- Solicita información del libro: título, autor, estado (Leyendo, Pendiente, Terminado), favorito (Sí/No), tipo y el ID del usuario.
- Clasifica libros en archivos por estado (`en_lectura.json`, `pendientes.json`, `acabados.json`).
- Actualiza el README del usuario con la información del libro añadido.

### Archivos generados/actualizados
- `Libros/[estado].json`
- `Libros/books.json`
- `Usuarios/[nombre]_[id]/README.md`

---

## **Cómo Usar**

### 1. Registrar un Usuario
1. Ve a la pestaña **Actions** en el repositorio.
2. Ejecuta el flujo de trabajo **Registrar Usuario** e ingresa los datos solicitados.

### 2. Añadir un Libro
1. En la pestaña **Actions**, ejecuta el flujo **Registrar Libro**.
2. Proporciona los detalles del libro y el ID del usuario.

---

## **Requisitos Previos**
- Tener `jq` instalado en el entorno para manipulación de archivos JSON.
- Organización de archivos en carpetas como `Libros/` y `Usuarios/`.
- Configuración de **secrets** en el repositorio para autenticación de GitHub Actions (`GITHUB_TOKEN`).

---

Este proyecto está diseñado para gestionar tu biblioteca de forma automatizada y escalable. ¡Disfruta gestionando tus usuarios y libros! 🚀
