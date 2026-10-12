# Ejercicio 14 - Modelo Entidad-Relación de un Sistema de Recetas de Cocina

## Descripción
Este ejercicio consiste en diseñar un modelo Entidad-Relación (DER) para un sistema de gestión de recetas de cocina. El modelo permite administrar miembros, recetas, ingredientes, pasos de preparación y reseñas dejadas por los usuarios.

## Entidades y atributos

### 1. Miembro
Representa a los usuarios registrados en la plataforma de cocina.
- **id_miembro**: identificador único del miembro.
- **nombre**: nombre del miembro.
- **mail**: correo electrónico de contacto.
- **contraseña**: credencial de acceso.
- **tipo perfil**: categoría o tipo de usuario.
- **fecha registro**: fecha de alta en la plataforma.

### 2. Receta
Representa las preparaciones culinarias publicadas en el sistema.
- **id_receta**: identificador único de la receta.
- **id_miembro**: identificador del miembro creador.
- **titulo**: título de la receta.
- **descripcion**: detalle de la preparación.
- **tiempo estimado**: duración estimada de elaboración.
- **porciones**: cantidad de porciones que rinde.
- **dificultad**: nivel de complejidad.

### 3. Ingrediente
Representa los alimentos o componentes utilizados en las recetas.
- **id_ingrediente**: identificador único del ingrediente.
- **medida**: unidad de medida estándar.
- **nombre**: nombre del ingrediente.
- **tipo**: categoría del alimento.
- **precio**: valor o costo estimado.

### 4. Rece_ingre
Entidad asociativa que vincula las recetas con sus ingredientes necesarios y cantidades.
- **id_receta**: identificador de la receta.
- **id_ingrediente**: identificador del ingrediente.
- **cantidad**: cantidad requerida del ingrediente.

### 5. Paso
Representa las etapas secuenciales para la elaboración de una receta.
- **id_paso**: identificador único del paso.
- **id_receta**: identificador de la receta asociada.
- **numero orden**: posición secuencial del paso.
- **descripcion**: explicación detallada de la acción a realizar.
- **cantidad pasos**: total de pasos de la receta.

### 6. Reseña
Representa las valoraciones y comentarios realizados por los miembros sobre las recetas.
- **id_reseña**: identificador único de la reseña.
- **id_miembro**: identificador del miembro que evalúa.
- **calificacion**: puntuación asignada.
- **comentario**: opinión textual del usuario.
- **fecha publicacion**: fecha en que se emitió la reseña.

## Relaciones y cardinalidades
- **Miembro – Receta (Pide / 1:N)**: un miembro puede crear y publicar múltiples recetas en la plataforma.
- **Receta – Ingrediente (Necesita / 1:N)**: una receta requiere de diversos ingredientes gestionados a través de la relación asociativa.
- **Receta – Paso (Tiene / 1:N)**: una receta se compone de múltiples pasos secuenciales.
- **Receta – Reseña (Consigue / 1:N)**: una receta recibe calificaciones y reseñas por parte de los usuarios.
- **Miembro – Reseña (Deja / 1:N)**: un miembro puede dejar varias reseñas en las diferentes recetas.

## Objetivo
Diseñar una base de datos para una plataforma de cocina que permita organizar recetas, administrar ingredientes y sus cantidades por plato, estructurar los pasos detallados de preparación, y gestionar las valoraciones y reseñas de la comunidad de usuarios.
