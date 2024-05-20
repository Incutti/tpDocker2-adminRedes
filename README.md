# Docker Multi Stage. Springboot con Java Maven
Integrantes: Mateo Incutti y Anna Mlikota

# Pasos a seguir
Lo primero que se debe hacer una vez clonado el repositorio es buildear la imagen.
  ```
  docker build -t nombreAEleccion .
  ```

Luego hay que correr un docker container asignándole la imagen creada.
  ```
  docker run -d -p 8080:8080 nombreAEleccion
  ```
Para abrirla en la web, se debe ingresar en el buscador 
  ```
  localhost:8080
  ```
