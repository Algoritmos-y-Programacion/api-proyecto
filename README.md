# **API de Laboratorio Químico**

Esta API provee datos básicos para un proyecto universitario de laboratorio químico. Sirve como **punto de partida** para cargar información inicial sobre reactivos, recetas (experimentos base) y experimentos realizados.

---

## **Contenido**

- [**API de Laboratorio Químico**](#api-de-laboratorio-químico)
  - [**Contenido**](#contenido)
  - [**Estructura de Archivos JSON**](#estructura-de-archivos-json)
  - [**Instalación y Uso**](#instalación-y-uso)
  - [**Endpoints Disponibles**](#endpoints-disponibles)

---

## **Estructura de Archivos JSON**

La API se basa en tres archivos principales:

1. **`reactivos.json`**
   - Contiene información de 50 reactivos con atributos como:
     - `id`, `nombre`, `descripcion`, `costo`, `categoria`, `inventario_disponible`, `unidad_medida`, `fecha_caducidad`, `minimo_sugerido`
     - Campo especial `conversiones_posibles` para convertir entre distintas unidades.
2. **`recetas.json`**
   - Almacena 30 “recetas base” o **plantillas de experimentos**, cada una con:
     - `id`, `nombre`, `objetivo`, `reactivos_utilizados`, `procedimiento`, `valores_a_medir` (con fórmulas y rangos).
3. **`experimentos.json`**
   - Lista 30 **instancias de experimentos** realizados, con:
     - `id`, `receta_id`, `personas_responsables`, `fecha`, `costo_asociado`, `resultado`.

Cada archivo está diseñado para **carga y persistencia** de datos. Se puede usar como fuente inicial en el sistema o conectarse a él a través de endpoints.

---

## **Instalación y Uso**

1. **Descarga** o **clona** este repositorio que contiene los archivos JSON.
2. Opcionalmente, configura un servidor (por ejemplo, con Node.js, Python Flask, etc.) que exponga estos archivos como endpoints de lectura/escritura.
3. Asegúrate de que las rutas a los archivos JSON sean correctas en tu aplicación.
4. En tu proyecto principal (el sistema de laboratorio químico), implementa las **operaciones CRUD** (Crear, Leer, Actualizar, Borrar) consultando a esta API (o directamente a los archivos JSON si no se hace un servidor REST).

---

## **Endpoints Disponibles**

> A continuación, usa este servidor principal `https://raw.githubusercontent.com/Algoritmos-y-Programacion/api-proyecto/refs/heads/main` que sirve los JSON.

- **Reactivos**

  - `GET /reactivos.json`
    Retorna la lista completa de reactivos.

- **Recetas**

  - `GET /recetas.json`
    Retorna la lista completa de recetas (experimentos base).

- **Experimentos**
  - `GET /experimentos.json`
    Retorna la lista de experimentos realizados.
