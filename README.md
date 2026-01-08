# Fractal Bloom: Generador de Arte

> *"Si el lenguaje tiene métrica, la naturaleza tiene Fractales."*

## Descripción
**Fractal Bloom** es una pieza de arte generativo interactiva construida con **HTML5 Canvas** y **JavaScript**. Este proyecto visualiza la belleza de las matemáticas a través de algoritmos recursivos, creando una estructura arbórea que se multiplica en un patrón caleidoscópico de 6 ejes.

A diferencia de las imágenes estáticas, este fractal está "vivo": utiliza una máquina de estados para simular un ciclo de respiración (crecimiento y decrecimiento) acompañado de una rotación perpetua y cambios de color.

## Tecnologías Utilizadas
* **Lenguaje:** JavaScript
* **Renderizado:** HTML5 Canvas API
* **Lógica Principal:** Funciones Recursivas

## Cómo Funciona (Lógica del Código)

El núcleo del proyecto reside en la función `drawBranch`. Esta función utiliza el principio de **recursividad** (una función que se llama a sí misma) para dibujar las ramas del árbol.

### 1. Recursividad y Caso Base
Cada rama se divide en dos nuevas ramas más pequeñas (`len * shrink`) en ángulos opuestos. El proceso se detiene cuando la profundidad (`depth`) alcanza el límite establecido, evitando bucles infinitos.

```javascript
function drawBranch(len, angle, depth) {
    // ... lógica de dibujo ...

    if (depth < maxDepth) {
        // Rama Derecha
        drawBranch(len * shrink, branchAngle, depth + 1);
        // Rama Izquierda
        drawBranch(len * shrink, -branchAngle, depth + 1);
    }
}
