markdown name=API.md
# 🔌 API Reference - Luba Beats

## Base URL
Development: http://localhost:3001 Production: https://api.lubaveats.com

Code

## Response Format

### Success

json
{
  "success": true,
  "data": { },
  "message": "Operación exitosa"
}
Error
JSON
{
  "success": false,
  "error": "ERROR_CODE",
  "message": "Descripción del error"
}


🔐 Authentication Endpoints
POST /api/auth/register
Registrar nuevo usuario

POST /api/auth/login
Iniciar sesión

POST /api/auth/logout
Cerrar sesión

👥 Users Endpoints
GET /api/users/:id
Obtener perfil

PUT /api/users/:id
Actualizar perfil

GET /api/users/:id/tracks
Obtener tracks del usuario

🎵 Tracks Endpoints
POST /api/tracks
Crear canción/beat

GET /api/tracks
Listar tracks

GET /api/tracks/:id
Obtener detalles

PUT /api/tracks/:id
Editar track

DELETE /api/tracks/:id
Eliminar track

❤️ Likes Endpoints
POST /api/tracks/:id/like
Dar like

DELETE /api/tracks/:id/like
Quitar like

GET /api/tracks/:id/likes
Obtener conteo

💬 Comments Endpoints
POST /api/tracks/:id/comments
Crear comentario

GET /api/tracks/:id/comments
Listar comentarios

DELETE /api/comments/:id
Eliminar comentario

🎧 Playlists & Favorites
