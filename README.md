
# 1 - ESQUEMA DE AUTH JWT

# Inicio de Sesión del Usuario: El usuario proporciona credenciales de inicio de sesión.
# Verificación de las Credenciales: Las credenciales son verificadas.
# Creación del Token JWT: Si las credenciales son válidas, se genera un token JWT y se devuelve al cliente.
# Almacenamiento del Token por el Cliente: El cliente almacena el token JWT.
# Envío del Token en Solicitudes Futuras: El token JWT se incluye en cada solicitud subsiguiente del cliente.
# Validación del Token JWT: El token es validado por la API.
# Autorización de Acceso: Si el token es válido, la API concede acceso a los recursos solicitados.
# Expiración y Renovación del Token JWT (Opcional): Los tokens pueden tener una fecha de expiración y se puede implementar un mecanismo de renovación.

# 2 - ENDPOINTS

# 2.1 - Login
http://localhost:5000/login

{
    "username": "isaac",
    "password": "123456"
}
return
# Use JWT token for authorization in the authentication header (Authorization).
{
    "access_token": "JWTTOKEN"  
}

# 2.2 - Obtener el tipo de un Pokémon (fuego, agua, tierra, aire, etc…) según su nombre.
http://localhost:5000/get_pokemon_info_by_name - POST

{
    "pokemon_name": "pikachu"
}

# 2.3 - Obtener un Pokémon al azar de un tipo en específico.
http://localhost:5000/get_random_pokemon_by_type - POST

{
    "pokemon_type": "fire"
}

# 2.4 - Obtener el Pokémon con nombre más largo de cierto tipo.
http://localhost:5000/get_longest_pokemon_name_by_type - POST

{
    "pokemon_type": "electric"
}

# 2.5 - Obtener un Pokémon al azar que contenga alguna de las letras ‘I’,’A’,’M’ en su nombre y que sea del tipo específico más fuerte en base al clima actual de tu ciudad.
http://localhost:5000/get_random_pokemon_by_city - GET

# 3 - Docker instructions

docker build -t pokeflaskapi .
docker run -p 5000:5000 pokeflaskapi

