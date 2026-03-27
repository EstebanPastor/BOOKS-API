📚 Books API (GOLang)

API REST simple para gestionar libros, desarrollada en Go usando arquitectura en capas.

Permite:

Crear libros
Listar todos los libros
Obtener un libro por ID
Actualizar libros
Eliminar libros
🧱 Estructura del proyecto

El proyecto sigue una arquitectura por capas:

internal/
├── model       # Definición de entidades (Book)
├── service     # Lógica de negocio
├── store       # Acceso a base de datos
└── transport   # Handlers HTTP

📌 Modelo
{
  "id": 1,
  "title": "string",
  "author": "string"
}
🚀 Endpoints
📚 Obtener todos los libros
GET /books
📘 Obtener libro por ID
GET /books/{id}
➕ Crear un libro
POST /books
Body
{
  "title": "El Principito",
  "author": "Antoine de Saint-Exupéry"
}

📌 Validación:

title es obligatorio
✏️ Actualizar un libro
PUT /books/{id}
Body
{
  "title": "Nuevo título",
  "author": "Nuevo autor"
}

📌 Validación:

title es obligatorio
❌ Eliminar un libro
DELETE /books/{id}
🗄️ Base de datos

La API utiliza una base de datos SQL con la siguiente tabla:

CREATE TABLE books (
  id INTEGER PRIMARY KEY AUTO_INCREMENT,
  title TEXT NOT NULL,
  author TEXT
);

⚠️ Manejo de errores
400 Bad Request → datos inválidos
404 Not Found → libro no encontrado
500 Internal Server Error → error interno
🛠️ Tecnologías
Go
net/http
database/sqlite

📦 Ejemplo de uso
curl http://localhost:8080/books
🧠 Notas
No incluye autenticación
Usa ? como placeholder SQL (compatible con MySQL / SQLite)
Arquitectura desacoplada mediante interfaces (Store)


👨‍💻 Autor

Esteban Pastor
