# Aplicación CRUD con Docker

Este repositorio contiene una aplicación CRUD empaquetada con Docker para facilitar su despliegue y ejecución.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalado:

- [Docker](https://www.docker.com/get-started)
- [Docker Compose](https://docs.docker.com/compose/install/)
- Git (opcional, para clonar el repositorio)

## Estructura del proyecto

```
├── docker-compose.yml
├── Dockerfile
├── src/
│   ├── controllers/
│   ├── models/
│   ├── routes/
│   └── index.js
├── package.json
└── README.md
```

## Instalación

### Opción 1: Clonar el repositorio

```bash
# Clonar el repositorio
git clone https://github.com/usuario/nombre-repositorio.git
cd nombre-repositorio
```

### Opción 2: Descargar como ZIP

1. Haz clic en el botón "Code" en la parte superior del repositorio
2. Selecciona "Download ZIP"
3. Extrae el archivo ZIP descargado
4. Navega hasta la carpeta extraída usando la terminal

## Configuración

El archivo `.env` contiene las variables de entorno necesarias para la aplicación. Si no existe, crea uno basado en el archivo `.env.example`:

```bash
cp .env.example .env
```

Edita el archivo `.env` según tus necesidades:

```
DB_HOST=db
DB_USER=usuario
DB_PASSWORD=contraseña
DB_NAME=nombre_db
PORT=3000
```

## Ejecución con Docker

### Construir y levantar los contenedores

Para construir y ejecutar la aplicación con Docker Compose:

```bash
docker-compose up
```

Para ejecutar los contenedores en segundo plano:

```bash
docker-compose up -d
```

La aplicación estará disponible en: `http://localhost:3000`

### Detener los contenedores

Para detener los contenedores manteniendo los datos:

```bash
docker-compose stop
```

Para detener y eliminar los contenedores:

```bash
docker-compose down
```

Si deseas eliminar también los volúmenes de datos:

```bash
docker-compose down -v
```

## Reconstrucción de la aplicación

Si has realizado cambios en el código y necesitas reconstruir la aplicación:

```bash
docker-compose build
docker-compose up
```

O en un solo comando:

```bash
docker-compose up --build
```

## API Endpoints

La API proporciona los siguientes endpoints:

- `GET /api/items` - Obtener todos los items
- `GET /api/items/:id` - Obtener un item específico
- `POST /api/items` - Crear un nuevo item
- `PUT /api/items/:id` - Actualizar un item existente
- `DELETE /api/items/:id` - Eliminar un item

## Solución de problemas

### Errores de conexión a la base de datos

Si encuentras errores de conexión a la base de datos, asegúrate de:

1. Verificar que las credenciales en el archivo `.env` sean correctas
2. Confirmar que el contenedor de la base de datos esté en ejecución:

```bash
docker-compose ps
```

### Errores de permisos

Si encuentras errores de permisos al ejecutar comandos de Docker:

```bash
sudo docker-compose up
```

O añade tu usuario al grupo de Docker:

```bash
sudo usermod -aG docker $USER
```

Luego, cierra sesión y vuelve a iniciarla para que los cambios surtan efecto.

## Contribuir

1. Haz un fork del repositorio
2. Crea una rama para tu función (`git checkout -b feature/amazing-feature`)
3. Realiza tus cambios
4. Haz commit de tus cambios (`git commit -m 'Añadir nueva funcionalidad'`)
5. Haz push a la rama (`git push origin feature/amazing-feature`)
6. Abre un Pull Request

##Capturas del funcionamiento
1. Login funcionando
![image](https://github.com/user-attachments/assets/7cd18bff-b88f-40e6-9843-3c582602dd60)
2. Menu principal
![image](https://github.com/user-attachments/assets/febb7a6d-e05a-4a2d-b8f6-920d08cf43ca)


## Licencia

Este proyecto está licenciado bajo [MIT License](LICENSE).
