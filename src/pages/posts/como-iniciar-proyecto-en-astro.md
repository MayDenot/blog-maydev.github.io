---
title: "¿Cómo iniciar un proyecto con Astro?"
layout: "../../layouts/BlogPostLayout.astro"
author: "Mayra Denot"
date: "09/09/23"
---

# ¿Cómo iniciar un proyecto con Astro? 🚀

09/09/23

#### Para utilizar Astro se necesita como versión mínima de Node Js la 14.15.1.

Para verificar que versión de node tenes, escribe en tu terminal:

```
node  -v
```

### <a id="1"></a> Para inicilizar el proyecto vamos a utilizar el asistente de configuración de Astro.

<span class="list">1</span> Abrir la terminal de su preferencia y ejecutar el siguiente comando utilizando tu gestor de paquetes favorito.

<span>npm</span> 
```
npm create astro@latest
```
<span>pnpm</span> 
```
pnpm create astro@latest
```
<span>yarn</span>
```
yarn create astro
```

<span class="list">2</span> Para confirmar ejecuta <span class="strong">y</span>.

<span class="list">3</span> A continuación tendrás que responder una serie de preguntas para configurar e instalar tu proyecto Astro según tus preferencias:

Aquí tendrás que escribir el nombre de tu proyecto, ya que viene uno por default:

![Ejemplo de que te aparecerá en la terminal.](../images/Astro1.png)

Tendrás que elegir cómo se estructurará tu proyecto, el recomendado es el primero y en caso de que quieras armarlo vos mismo, elige la opción de empty (vacío).

![Las preguntas que deberían salirte sobre los templates de tu proyecto.](../images/Astro2.png)

Te preguntará si quieres instalar las dependencias, lo recomendado es que si las instales y siempre.

![Dependencias 'Si' o 'No'.](../images/Astro3.png)

Si quieres usar TypeScript elige que sí, aunque esta opción luego podrás cambiarla manualmente en caso de arrepentirte.

![Usaras TypeScript 'Si' o 'No'.](../images/Astro4.png)

Te preguntará qué tan estricto debería ser TypeScript, la recomendada es Strict, pero en caso de no estar seguro de usarlo, puedes elegir la opción de Relaxed.

![Como quieres usar TypeScript.](../images/Astro5.png)

Y por último, te preguntará si quieres inicializar este proyecto en un repositorio de Git, como esta pregunta es opcional, recomiendo poner que No y en caso de arrepentirte podrás inicializar luego manualmente el repositorio.

![Repositorio de Git 'Si' o 'No' (Opcional).](../images/Astro6.png)

Finalmente accederás a la carpeta de tu proyecto, con los comando cd "nombredetuproyecto"

Se tendría que ver algo así:

![Rutas de como debería quedar tu terminal.](../images/Astro8.png)

Para abrir tu proyecto en tu editor de código ejecuta el comando <span class="strong">code .</span>.

![Abrir editor de código desde la terminal.](../images/Astro7.png)

### <a id="2"></a> Para ejecutar Astro en modo desarrollo, ejecuta en la terminal el siguiente comando utilizando tu gestor de paquetes favorito:

<span>npm</span>
```
npm run dev
```
<span>pnpm</span>
```
pnpm run dev
```
<span>yarn</span>
```
yarn run dev
```

Ahora te aparecerá en la terminal la confirmación de Astro que está siendo ejecutado en modo dev (desarrollo).

![Confirmación de Astro, con el enlace para visualizar la página.](../images/Astro9.png)

### <a id="3"></a> Visualizar nuestro proyecto en el navegador

Para visualizar tu proyecto en tu navegador haz click en la parte de tu terminal donde dice Local, u otra opción es escribir manualmente la dirección.

![Página por default de Astro en el navegador.](../images/Astro10.png)