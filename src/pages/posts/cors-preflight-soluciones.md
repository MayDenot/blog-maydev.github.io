---
title: "¿Qué es el CORS, Preflight y soluciones?"
layout: "../../layouts/BlogPostLayout.astro"
author: "Mayra Denot"
date: "12/09/23"
ancors: [
  {id: 4}, 
  {id: 5}, 
  {id: 6}, 
  {id: 7}, 
  {id: 8}, 
  {id: 9}
]
articleHeadings: [
  {subtitles: "¿Qué significa CORS?"}, 
  {subtitles: "¿Cómo funciona?"}, 
  {subtitles: "¿Cómo podemos identificar si se trata de un problema de CORS?"},
  {subtitles: "SOLUCIÓN del CORS Simple"},    
  {subtitles: "¿Qué es el CORS Preflight?"},
  {subtitles: "SOLUCIÓN"}
]
---

<section class="cors-art">

# ¿Qué es el CORS, Preflight y SOLUCIONES?

12/09/23

### <a id="4"></a> ¿Qué significa CORS?

Cross Origin Resource Sharing o intercambio de recursos de orígen cruzado (CORS) es un error que se presenta en los navegadores y que debe ser solucionado por el lado del servidor (backend).

### <a id="5"></a> ¿Cómo funciona?

El CORS es un mecanismo que está respaldado por las cabeceras o headers HTTP, los cuales permiten a los servidores indicarles a los navegadores si tienen que permitir cargar recursos (imágenes, vídeos, fuentes, css, étc) para otro orígen.

Los orígenes pueden ser dominios, esquemas o puertos. 

Para comprender mejor les dejo un gráfico con el flujo del CORS:

![Flujo del CORS](/assets/FlujoCORS.jpg)

### <a id="6"></a> ¿Cómo podemos identificar si se trata de un problema de CORS?

Hay dos maneras, la más fácil y “visible” o accesible es abriendo las DevTools y en la consola nos aparecerá un mensaje como el siguiente.

![Error CORS en consola](/assets/DevToolsCORSConsola.jpg)

Y la otra es desde las DevTools, vamos a ir a la parte superior donde dice Network o Red (recargamos la página con F5 para asegurarnos de que aparezcan las peticiones).

![Barra superior de las DevTools situados en Network o Red](/assets/DevToolsCORSNet.jpg)

Y luego más abajo se podrán ver muchas o algunas peticiones con sus respectivos nombres y demás características. Dentro de esas características nos centraremos en donde dice Status o Estado, si es un problema de CORS va a decir Error CORS.

![Error CORS desde la Red](/assets/DevToolsCORSStatus.jpg)

### <a id="7"></a> SOLUCIÓN del CORS Simple

Para solucionarlo tendremos que agregar a la petición correspondiente el encabezado, en caso de la imagen anterior se puede ver que la petición es /movies.

Solución NO recomendada:
<div class="cors-solution">

```javascript
app.get('/movies', (req, res) => {
  res.header('Access-Control-Allow-Origin', '*');
  // resto de su código
});
```
</div>

El * significa que le damos acceso a TODOS los orígenes, mientras que no sea nuestro propio orígen.

Solución recomendada:
<div class="cors-solution">

```javascript
app.get('/movies', (req, res) => {
  res.header('Access-Control-Allow-Origin', 'orígen al que le queres dar acceso');
  // resto de su código
});
```
</div>

En caso de que queramos que múltiples orígenes puedan acceder a nuestro orígen (supongamos que es una API), podríamos crear una variable y guardar en ella todos los orígenes que tienen permitido acceder.

<div class="cors-solution">

```javascript
const ACCEPTED_ORIGINS = {
  'https://localhost:3000',
  'https://localhost:9000',
  'https://youtube.com'
}
```
</div>

Y luego recuperamos el origin del header.

<div class="cors-solution">

```javascript
app.get('/movies', (req, res) => {
  const origin = req.header('origin');
  if (ACCEPTED_ORIGINS.includes(orgin)) {
    res.header('Access-Control-Allow-Origin', 'orígen al que le queres dar acceso');
    // resto de su código
  }
});
```
</div>

Algo importante a recalcar es que no siempre el navegador te enviará el header de origin, cuando la petición es del mismo origin, el navegador no enviará el header. 

Para prevenir esto:
<div class="cors-solution">

```javascript
app.get('/movies', (req, res) => {
  const origin = req.header('origin');
  if (ACCEPTED_ORIGINS.includes(origin) || !origin) {
    res.header('Access-Control-Allow-Origin', 'orígen al que le queres dar acceso');
    // resto de su código
  }
});
```
</div>

### <a id="8"></a> ¿Qué es el CORS Preflight?

El CORS preflight es un método complejo al igual que PUT, DELETE y PATCH.
Cuando hacemos una petición (request) PUT, PATCH o DELETE, necesitaremos otra petición especial llamada OPTIONS. Con ella le indicaremos que antes de que se ejecute cualquiera de los tres verbos anteriormente nombrados (PUT, PATCH o DELETE) que avise que lo va hacer.

Ejemplo con DELETE:

![Ejemplo como se ve el CORS Preflight desde las DevTools](/assets/CORSPREFLIGHT.png)

Primero aparecerá el error CORS y debajo el OPTIONS (preflight).

### <a id="9"></a> SOLUCIÓN

A nuestra aplicación le agregaremos el verbo OPTIONS como cualquier otro método (GET, PUT, etc). Y dentro le pasaremos la misma solución que en el CORS simple, pero con esto no alcanzará, por lo que debemos sumarle otro header que le indique que otros métodos podrá utilizar también.

<div class="cors-solution">

```javascript
app.get('/movies:id', (req, res) => {
  const origin = req.header('origin');
  if (ACCEPTED_ORIGINS.includes(origin) || !origin) {
    res.header('Access-Control-Allow-Origin', 'orígen al que le queres dar acceso');
    res.header('Access-Control-Allow-Methods', 'GET, POST, PUT, PATCH, DELETE');
    // resto de su código
  }
  res.send(200);
});
```
</div>

</section>