# **Documentation in Spanish**

Una librería de JavaScript ultraligera y sin dependencias para crear carruseles de imágenes dinámicos de forma automática.

Este script transforma una lista plana de imágenes en un carrusel interactivo con controles de navegación, gestionando automáticamente la estructura del DOM y los estilos necesarios.
Características:

- Zero Dependencies: No requiere jQuery ni frameworks externos.

- Auto-Inyectado: Genera automáticamente el contenedor interno y los botones de control.

- Transiciones Suaves: Animaciones fluidas mediante CSS transitions.

- Diseño Limpio: Estética minimalista con controles flotantes.

**Instalación y Uso**

**1. Estructura HTML**
Solo necesitas un contenedor con la clase .alfredocarrusel y las imágenes que quieras mostrar dentro:

---
```
<div class="alfredocarrusel">
    <img src="imagen1.jpg" alt="Slide 1">
    <img src="imagen2.jpg" alt="Slide 2">
    <img src="imagen3.jpg" alt="Slide 3">
</div>
```
---

**2. CSS Requerido**
Asegúrate de incluir estos estilos en tu archivo .css para garantizar el correcto funcionamiento del desplazamiento y el posicionamiento de los botones:

---
```
/* Contenedor principal */
.alfredocarrusel {
    width: 1280px;
    height: 720px;
    overflow: hidden;
    position: relative; 
}

/* Contenedor dinámico de imágenes */
.alfredocarrusel section {
    display: flex;
    width: fit-content;
    position: relative; 
    left: 0px;
    transition: all 1s;
}

.alfredocarrusel section img {
    width: 1280px;
    height: 720px;
    object-fit: cover; 
}

/* Controles de navegación */
button {
    border: none;
    background: rgba(255,255,255,0.5);
    width: 50px;
    height: 50px;
    position: absolute;
    border-radius: 60px;
    font-size: 30px;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
    cursor: pointer;
}

button:hover {
    background: rgba(255,255,255,1);
    transition: all 0.3s;
}

button:last-child {
    right: 0;
}
```
---

**3. Lógica (JavaScript)**

Añade el script al final de tu <body>. El script se encarga de reestructurar el HTML para crear la tira de imágenes necesaria para el efecto de deslizamiento.
Cómo funciona internamente

- Limpieza del DOM: El script detecta las imágenes originales, las extrae temporalmente y limpia el contenedor.

- Reestructuración: Crea un elemento <section> (el "riel" del carrusel) y reinserta las imágenes dentro.

- Controles: Genera e inyecta los botones ◀ y ▶ con eventos onclick vinculados.

- Cálculo de desplazamiento: Utiliza una variable contador y una variable anchura (1280px) para calcular la propiedad left del riel.
---
**Personalización**

Puedes ajustar estas variables en el código JS para adaptar el carrusel a tus necesidades:
```
Variable |	Descripción	Valor por defecto
anchura |	El ancho en píxeles de cada imagen.	1280
contador < -7 |	Límite de imágenes (ajustar según cantidad de fotos).	-7
```

# **Documentation in English**

An ultra-lightweight, dependency-free JavaScript library for automatically creating dynamic image carousels.

This script transforms a flat list of images into an interactive carousel with navigation controls, automatically managing the DOM structure and the necessary styles.
Features:

- Zero Dependencies: Does not require jQuery or external frameworks.

- Auto-Injected: Automatically generates the internal container and control buttons.

- Smooth Transitions: Fluid animations using CSS transitions.

- Clean Design: Minimalist aesthetic with floating controls.

**Installation and Usage**

**1. HTML Structure**
You only need a container with the class .alfredocarrusel and the images you want to display inside:

---
```
<div class="alfredocarrusel">
    <img src="imagen1.jpg" alt="Slide 1">
    <img src="imagen2.jpg" alt="Slide 2">
    <img src="imagen3.jpg" alt="Slide 3">
</div>
```
---
**2. Required CSS**
Make sure to include these styles in your .css file to ensure proper scrolling behavior and correct button positioning:

---
```
/* Contenedor principal */
.alfredocarrusel {
    width: 1280px;
    height: 720px;
    overflow: hidden;
    position: relative; 
}

/* Contenedor dinámico de imágenes */
.alfredocarrusel section {
    display: flex;
    width: fit-content;
    position: relative; 
    left: 0px;
    transition: all 1s;
}

.alfredocarrusel section img {
    width: 1280px;
    height: 720px;
    object-fit: cover; 
}

/* Controles de navegación */
button {
    border: none;
    background: rgba(255,255,255,0.5);
    width: 50px;
    height: 50px;
    position: absolute;
    border-radius: 60px;
    font-size: 30px;
    top: 50%;
    transform: translateY(-50%);
    z-index: 10;
    cursor: pointer;
}

button:hover {
    background: rgba(255,255,255,1);
    transition: all 0.3s;
}

button:last-child {
    right: 0;
}
```
---
**3. Logic (JavaScript)**

Add the script at the end of your <body>. The script is responsible for restructuring the HTML to create the image strip needed for the sliding effect.
How it works internally

- DOM Cleanup: The script detects the original images, temporarily extracts them, and clears the container.

- Restructuring: Creates a <section> element (the carousel "rail") and reinserts the images inside.

- Controls: Generates and injects the ◀ and ▶ buttons with bound onclick events.

- Offset Calculation: Uses a counter variable and a width variable (1280px) to calculate the left property of the rail.
---
**Customization**

You can adjust these variables in the JS code to adapt the carousel to your needs:
```
Variable |	Descripción	Valor por defecto
anchura |	El ancho en píxeles de cada imagen.	1280
contador < -7 |	Límite de imágenes (ajustar según cantidad de fotos).	-7
```
